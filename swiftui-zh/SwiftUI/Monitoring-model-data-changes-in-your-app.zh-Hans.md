--- 来源：https://developer.apple.com/documentation/SwiftUI/Monitoring-model-data-changes-in-your-app

抓取时间：2025-12-02T15:51:17Z

---

# 监控应用中的数据变更

**示例代码**

使用可观察对象在应用的用户界面中显示数据变更。

## 概述

通常，您会使用一个独立于应用用户界面 (UI) 和其他逻辑的数据模型来存储和处理应用中的数据。这种分离有助于提高模块化程度，增强可测试性，并让您更容易理解应用的工作原理。

传统上，您会使用视图控制器在模型和 UI 之间来回传递数据，但 SwiftUI 会为您处理大部分同步工作。要在数据变更时更新视图，您可以将数据模型类设为可观察对象，发布它们的属性，并使用属性包装器声明它们的实例。为了确保用户驱动的数据更改能够反馈到模型中，您需要将 UI 控件绑定到模型属性。这些功能协同工作，有助于维护数据的单一数据源。

### 使模型数据可观察

要使 SwiftUI 能够感知模型中的数据更改，请为模型类采用 [doc://com.apple.documentation/documentation/Combine/ObservableObject] 协议。例如，您可以创建一个 `Book` 类，该类是一个可观察对象：

```swift
class Book: ObservableObject {
}
```

系统会自动推断该类的 [doc://com.apple.documentation/documentation/Combine/ObservableObject/ObjectWillChangePublisher] 关联类型，并合成所需的 [doc://com.apple.documentation/documentation/Combine/ObservableObject/objectWillChange] 方法，该方法会发出已发布属性的更改值。要发布属性，请将 [doc://com.apple.documentation/documentation/Combine/Published] 属性包装器添加到属性声明中：

```swift
class Book: ObservableObject {
    @Published var title = "Sample Book Title"
}
```

避免在不需要时发布属性带来的额外开销。仅发布那些既可以更改又对 UI 至关重要的属性。例如，`Book` 类可能有一个 `identifier` 属性，该属性在初始化后永远不会更改：

```swift
class Book: ObservableObject {
    @Published var title = "Sample Book Title"

    let identifier = UUID() // A unique identifier that never changes.
}
```

您仍然可以在用户界面中显示该标识符，但由于它未发布，SwiftUI 不会监视该特定属性的更改。

### 监控可观察对象的变化

要让 SwiftUI 监控一个可观察对象，请在属性声明中添加 [ObservedObject](ObservedObject.zh-Hans.md) 属性包装器：

```swift
struct BookView: View {
    @ObservedObject var book: Book
    
    var body: some View {
        Text(book.title)
    }
}
```

您可以将被观察对象的各个属性传递给子视图，如上所示。当数据发生变化时（例如从磁盘加载新数据时），SwiftUI 会更新所有受影响的视图。您还可以将整个可观察对象传递给子视图，并在视图层次结构的不同层级之间共享模型对象：

```swift
struct BookView: View {
    @ObservedObject var book: Book
    
    var body: some View {
        BookEditView(book: book)
    }
}

struct BookEditView: View {
    @ObservedObject var book: Book

    // ...
}
```

### 在视图中实例化模型对象

SwiftUI 随时可能创建或重新创建视图，因此，使用给定的一组输入初始化视图时，确保始终生成相同的视图至关重要。因此，在视图内部创建被观察对象是不安全的。相反，SwiftUI 提供了 [StateObject](StateObject.zh-Hans.md) 属性包装器，它为存储在视图层级结构中的引用类型创建了一个单一数据源。您可以像这样在视图中安全地创建 `Book` 实例：

```swift
struct LibraryView: View {
    @StateObject private var book = Book()
    
    var body: some View {
        BookView(book: book)
    }
}
```

状态对象的行为类似于观察对象，不同之处在于，无论视图被重新创建多少次，SwiftUI 都会为每个视图实例创建并管理一个单独的对象实例。您可以本地使用该对象，也可以将状态对象传递给另一个视图的观察对象属性，如上面的示例所示。

虽然 SwiftUI 不会在视图中重新创建状态对象，但它会为每个视图实例创建一个独立的对象实例。例如，以下代码中的每个 `LibraryView` 都会获得一个唯一的 `Book` 实例：

```swift
VStack {
    LibraryView()
    LibraryView()
}
```

您还可以在顶层 [App](App.zh-Hans.md) 实例中，或在应用程序的某个 [Scene](Scene.zh-Hans.md) 实例中创建状态对象。例如，如果您定义了一个名为 `Library` 的可观察对象，用于存储图书阅读器应用中的书籍集合，则可以在应用的顶层结构中创建一个单独的库实例：

```swift
@main
struct BookReader: App {
    @StateObject private var library = Library()

    // ...
}
```

### 在应用中共享对象

如果您有一个数据模型对象，希望在整个应用中使用，但又不想让它经过多层层级，则可以使用 [environmentObject(_:)](View/environmentObject.zh-Hans.md) 视图修饰符将该对象放入环境中：

```swift
@main
struct BookReader: App {
    @StateObject private var library = Library()
    
    var body: some Scene {
        WindowGroup {
            LibraryView()
                .environmentObject(library)
        }
    }
}
```

应用此修饰符的视图的任何子视图都可以通过使用 [EnvironmentObject](EnvironmentObject.zh-Hans.md) 属性包装器声明属性来访问数据模型实例：

```swift
struct LibraryView: View {
    @EnvironmentObject var library: Library
    
    // ...
}
```

如果您使用环境对象，则可以将其添加到应用层级结构顶部的视图中，如上所示。或者，您可以将其添加到视图层次结构中子树的根视图。无论哪种方式，请记住还要将其添加到使用该对象的任何视图或其后代视图的预览提供程序中：

```swift
struct LibraryView_Previews: PreviewProvider {
    static var previews: some View {
        LibraryView()
            .environmentObject(Library())
    }
}
```

### 使用绑定创建双向连接

当您允许用户更改 UI 中的数据时，请使用绑定到相应的属性。这可确保更新自动流回数据模型。您可以通过在对象名称前加上美元符号 (`$`) 来获取对观察对象、状态对象或环境对象属性的绑定。例如，如果您允许用户通过在 `BookEditView` 中添加 [TextField](TextField.zh-Hans.md) 来编辑书籍标题，请将文本字段绑定到书籍的 `title` 属性：

```swift
struct BookEditView: View {
    @ObservedObject var book: Book
    
    var body: some View {
        TextField("Title", text: $book.title)
    }
}
```

此绑定将视图元素连接到底层模型，以便用户可以直接修改模型数据。

## 创建模型数据

- **管理应用中的模型数据**：创建应用数据模型和视图之间的连接。

- **从 Observable Object 协议迁移到 Observable 宏**：更新现有应用以利用 Swift 中 Observation 的优势。

- **Observable()**：定义并实现 Observable 协议的一致性。

- **StateObject**：实例化 Observable 对象的属性包装类型。

- **ObservedObject**：一种属性包装器类型，它订阅一个可观察对象，并在该可观察对象发生更改时使视图失效。

- **ObservableObject**：一种带有发布者的对象类型，该发布者会在对象发生更改之前发出消息。


---
source: https://developer.apple.com/documentation/SwiftUI/Monitoring-model-data-changes-in-your-app
crawled: 2025-12-02T15:51:17Z
---

# Monitoring data changes in your app

**Sample Code**

Show changes to data in your app’s user interface by using observable objects.

## Overview

You typically store and process data in your app using a data model that’s separate from your app’s user interface (UI) and other logic. The separation promotes modularity, improves testability, and makes it easier to reason about how your app works.

Traditionally, you use a view controller to move data back and forth between the model and the UI, but SwiftUI handles most of this synchronization for you. To update views when data changes, you make your data model classes observable objects, publish their properties, and declare instances of them using property wrappers. To ensure user-driven data changes flow back into the model, you bind UI controls to model properties. Working together, these features help you to maintain a single source of truth for your data.



### Make model data observable

To make the data changes in your model visible to SwiftUI, adopt the [doc://com.apple.documentation/documentation/Combine/ObservableObject] protocol for model classes. For example, you can create a `Book` class that’s an observable object:

```swift
class Book: ObservableObject {
}
```

The system automatically infers the [doc://com.apple.documentation/documentation/Combine/ObservableObject/ObjectWillChangePublisher] associated type for the class and synthesizes the required [doc://com.apple.documentation/documentation/Combine/ObservableObject/objectWillChange] method that emits the changed values of published properties. To publish a property, add the [doc://com.apple.documentation/documentation/Combine/Published] property wrapper to the property’s declaration:

```swift
class Book: ObservableObject {
    @Published var title = "Sample Book Title"
}
```

Avoid the overhead of a published property when you don’t need it. Only publish properties that both can change and that matter to the UI. For example, the `Book` class might have an `identifier` property that never changes after initialization:

```swift
class Book: ObservableObject {
    @Published var title = "Sample Book Title"

    let identifier = UUID() // A unique identifier that never changes.
}
```

You can still display the identifier in your user interface, but because it isn’t published, SwiftUI doesn’t watch that particular property for changes.

### Monitor changes in observable objects

To tell SwiftUI to monitor an observable object, add the [ObservedObject](ObservedObject.zh-Hans.md) property wrapper to the property’s declaration:

```swift
struct BookView: View {
    @ObservedObject var book: Book
    
    var body: some View {
        Text(book.title)
    }
}
```

You can pass individual properties of an observed object to child views, as shown above. When the data changes, like when you load new data from disk, SwiftUI updates all the affected views. You can also pass an entire observable object to a child view and share model objects across levels of a view hierarchy:

```swift
struct BookView: View {
    @ObservedObject var book: Book
    
    var body: some View {
        BookEditView(book: book)
    }
}

struct BookEditView: View {
    @ObservedObject var book: Book

    // ...
}
```

### Instantiate a model object in a view

SwiftUI might create or recreate a view at any time, so it’s important that initializing a view with a given set of inputs always results in the same view. As a result, it’s unsafe to create an observed object inside a view. Instead, SwiftUI provides the [StateObject](StateObject.zh-Hans.md) property wrapper, which creates a single source of truth for a reference type that you store in a view hierarchy. You can safely create a `Book` instance inside a view this way:

```swift
struct LibraryView: View {
    @StateObject private var book = Book()
    
    var body: some View {
        BookView(book: book)
    }
}
```

A state object behaves like an observed object, except that SwiftUI creates and manages a single object instance for a given view instance, regardless of how many times it recreates the view. You can use the object locally, or pass the state object into another view’s observed object property, as shown in the above example.

While SwiftUI doesn’t recreate the state object within a view, it does create a distinct object instance for each view instance. For example, each `LibraryView` in the following code gets a unique `Book` instance:

```swift
VStack {
    LibraryView()
    LibraryView()
}
```

You can also create a state object in your top level [App](App.zh-Hans.md) instance, or in one of your app’s [Scene](Scene.zh-Hans.md) instances. For example, if you define an observable object called `Library` to hold a collection of books for a book reader app, you could create a single library instance in the app’s top level structure:

```swift
@main
struct BookReader: App {
    @StateObject private var library = Library()

    // ...
}
```

### Share an object throughout your app

If you have a data model object that you want to use throughout your app, but don’t want to pass it through many layers of hierarchy, you can use the [environmentObject(_:)](View/environmentObject.zh-Hans.md) view modifier to put the object into the environment instead:

```swift
@main
struct BookReader: App {
    @StateObject private var library = Library()
    
    var body: some Scene {
        WindowGroup {
            LibraryView()
                .environmentObject(library)
        }
    }
}
```

Any descendant view of the view to which you apply the modifier can then access the data model instance by declaring a property with the [EnvironmentObject](EnvironmentObject.zh-Hans.md) property wrapper:

```swift
struct LibraryView: View {
    @EnvironmentObject var library: Library
    
    // ...
}
```

If you use an environment object, you might add it to the view at the top of your app’s hierarchy, as shown above. Alternatively, you might add it to the root view of a subtree in your view hierarchy. Either way, remember to also add it to the preview provider of any view that uses the object, or that has a descendant that uses the object:

```swift
struct LibraryView_Previews: PreviewProvider {
    static var previews: some View {
        LibraryView()
            .environmentObject(Library())
    }
}
```

### Create a two-way connection using bindings

When you allow a person to change the data in the UI, use a binding to the corresponding property. This ensures that updates flow back into the data model automatically. You can get a binding to an observed object, state object, or environment object property by prefixing the name of the object with the dollar sign (`$`). For example, if you let someone edit the title of a book by adding a [TextField](TextField.zh-Hans.md) to the `BookEditView`, give the text field a binding to the book’s `title` property:

```swift
struct BookEditView: View {
    @ObservedObject var book: Book
    
    var body: some View {
        TextField("Title", text: $book.title)
    }
}
```

The binding connects the view element to the underlying model so that a person makes changes directly to the model data.

## Creating model data

- **Managing model data in your app**: Create connections between your app’s data model and views.
- **Migrating from the Observable Object protocol to the Observable macro**: Update your existing app to leverage the benefits of Observation in Swift.
- **Observable()**: Defines and implements conformance of the Observable protocol.
- **StateObject**: A property wrapper type that instantiates an observable object.
- **ObservedObject**: A property wrapper type that subscribes to an observable object and invalidates a view whenever the observable object changes.
- **ObservableObject**: A type of object with a publisher that emits before the object has changed.

