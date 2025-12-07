---

来源：https://developer.apple.com/documentation/swiftui/managing-model-data-in-your-app

抓取时间：2025-12-04T18:54:30Z

---

# 管理应用中的模型数据

**示例代码**

创建应用数据模型和视图之间的连接。

## 概述

SwiftUI 应用可以显示用户可以通过应用的用户界面 (UI) 修改的数据。为了管理这些数据，应用会创建一个数据模型，这是一种表示数据的自定义类型。数据模型将数据与操作数据的视图分离。这种分离有助于提高模块化程度，增强可测试性，并帮助用户更轻松地理解应用的工作原理。

保持模型数据（即数据模型的实例）与屏幕上显示的内容同步可能具有挑战性，尤其是在数据同时出现在 UI 的多个视图中时。

SwiftUI 借助 Observation 功能，能够让应用的 UI 与数据变化保持同步。通过 [doc://com.apple.documentation/documentation/Observation]，SwiftUI 中的视图可以依赖于可观察的数据模型，并在数据发生变化时更新 UI。

### 使模型数据可观察

要使 SwiftUI 能够感知数据变化，请将 [doc://com.apple.documentation/documentation/Observation/Observable()] 宏应用于数据模型。此宏会在编译时生成代码，为数据模型添加观察支持，从而使数据模型代码专注于存储数据的属性。例如，以下代码定义了一个书籍的数据模型：

```swift
@Observable class Book: Identifiable {
    var title = "Sample Book Title"
    var author = Author()
    var isAvailable = true
}
```

### 在视图中观察模型数据

在 SwiftUI 中，当视图的 [body-8kl5o](View/body-8kl5o.zh-Hans.md) 属性读取可观察数据模型对象（例如 `Book` 的实例）的属性时，视图便会依赖于该对象。如果 `body` 没有读取任何可观察数据模型对象的属性，则视图不会跟踪任何依赖项。

当跟踪的属性发生变化时，SwiftUI 会更新视图。如果其他 [body-8kl5o](View/body-8kl5o.zh-Hans.md) 没有读取的属性发生变化，则视图不受影响，从而避免不必要的更新。例如，以下代码中的视图仅在书籍的 `title` 发生变化时更新，而不会在 `author` 或 `isAvailable` 发生变化时更新：

```swift
struct BookView: View {
    var book: Book
    
    var body: some View {
        Text(book.title)
    }
}
```

即使视图不存储可观察类型（例如，使用全局属性或单例时），SwiftUI 也会建立这种依赖项跟踪：

```swift
var globalBook: Book = Book()

struct BookView: View {
    var body: some View {
        Text(globalBook.title)
    }
}
```

当计算属性使用可观察属性时，观察也支持跟踪计算属性。例如，以下代码中的视图会在可用书籍数量发生变化时更新：

```swift
@Observable class Library {
    var books: [Book] = [Book(), Book(), Book()]
    
    var availableBooksCount: Int {
        books.filter(\.isAvailable).count
    }
}

struct LibraryView: View {
    @Environment(Library.self) private var library
    
    var body: some View {
        NavigationStack {
            List(library.books) { book in
                // ...
            }
            .navigationTitle("Books available: \(library.availableBooksCount)")
        }
    }
}
```

当视图依赖于任何集合类型的对象集合时，该视图会跟踪集合本身的更改。例如，以下代码中的视图依赖于 `books`，因为 `body` 会读取它。当 `books` 发生更改时（例如在集合中插入、删除、移动或替换项），SwiftUI 会更新视图。

```swift
struct LibraryView: View {
    @State private var books = [Book(), Book(), Book()]

    var body: some View {
        List(books) { book in 
            Text(book.title)
        }
    }
}
```

但是，`LibraryView` 不会依赖于属性 `title`，因为视图的 [body-8kl5o](View/body-8kl5o.zh-Hans.md) 不会直接读取它。视图将内容闭包存储为闭包，SwiftUI 会在列表项延迟显示在屏幕上之前调用该闭包。这意味着，列表中的每个项不再依赖于书籍的闭包，而是依赖于自身的闭包。对闭包的任何更改只会更新代表该书籍的闭包，而不会更新其他闭包。

您还可以与其他视图共享可观察模型数据对象。如果接收视图读取了该对象的任何属性，则会形成依赖关系。例如，在以下代码中，`LibraryView` 与 `BookView` 共享 `Book` 的一个实例，而 `BookView` 显示该书的 `title`。如果该书的 `title` 发生变化，SwiftUI 只会更新 `BookView`，而不会更新 `LibraryView`，因为只有 `BookView` 读取 `title` 属性。

```swift
struct LibraryView: View {
    @State private var books = [Book(), Book(), Book()]

    var body: some View {
        List(books) { book in 
            BookView(book: book)
        }
    }
}

struct BookView: View {
    var book: Book
    
    var body: some View {
        Text(book.title)
    }
}
```

如果视图没有任何依赖项，SwiftUI 不会在数据发生变化时更新该视图。这种方法允许可观察模型数据对象在视图层次结构的多个层级之间传递，而无需每个中间视图都形成依赖关系。

```swift
// Will not update when any property of `book` changes.
struct LibraryView: View {
    @State private var books = [Book(), Book(), Book()]
    
    var body: some View {
        LibraryItemView(book: book)
    }
}

// Will not update when any property of `book` changes.
struct LibraryItemView: View {
    var book: Book
    
    var body: some View {
        BookView(book: book)
    }
}

// Will update when `book.title` changes.
struct BookView: View {
    var book: Book
    
    var body: some View {
        Text(book.title)
    }
}
```

然而，如果视图存储了对可观察对象的引用，并且该引用发生变化，则视图也会更新。这是因为存储的引用是视图值的一部分，而不是因为对象本身是可观察的。例如，如果以下代码中对 book 的引用发生变化，SwiftUI 会更新视图：

```swift
struct BookView: View {
    var book: Book
    
    var body: some View {
        // ...
    }
}
```

视图还可以依赖于通过另一个对象访问的可观察数据模型对象。例如，当 author 的值发生变化时，以下代码中的视图会更新：`name`

```swift
struct LibraryItemView: View {
    var book: Book
    
    var body: some View {
        VStack(alignment: .leading) {
            Text(book.title)
            Text("Written by: \(book.author.name)")
                .font(.caption)
        }
    }
}
```

### 创建模型数据的真实来源

要创建并存储模型数据的真实来源，请声明一个私有变量，并使用可观察数据模型类型的实例对其进行初始化。然后，使用属性包装器将其包装起来。[State](State.zh-Hans.md)例如，以下代码将数据模型类型 `Book` 的一个实例存储在状态变量 `book` 中：

```swift
struct BookView: View {
    @State private var book = Book()
    
    var body: some View {
        Text(book.title)
    }
}
```

通过使用 [State](State.zh-Hans.md) 包裹该对象，您可以指示 SwiftUI 管理该实例的存储。每次 SwiftUI 重新创建 `BookView` 时，它都会将 `book` 变量连接到托管实例，从而为视图提供模型数据的单一数据源。

您还可以在顶级 [App](App.zh-Hans.md) 实例或应用程序的某个 [Scene](Scene.zh-Hans.md) 实例中创建状态对象。例如，以下代码在应用程序的顶层结构中创建了 `Library` 的实例：

```swift
@main
struct BookReaderApp: App {
    @State private var library = Library()
    
    var body: some Scene {
        WindowGroup {
            LibraryView()
                .environment(library)
        }
    }
}
```

### 在视图层级结构中共享模型数据

如果您有一个数据模型对象（例如 `Library`），并且希望在整个应用程序中共享它，您可以：

- 将数据模型对象传递给视图层级结构中的每个视图；或者

- 将数据模型对象添加到视图的环境中

当视图层级结构较浅时，例如，当视图不与其子视图共享对象时，将模型数据传递给每个视图非常方便。但是，您通常不知道视图是否需要将对象传递给子视图，也不知道层级结构深处的子视图是否需要模型数据。

要在视图层级结构中共享模型数据而无需将其传递给每个视图，请将模型数据添加到视图的环境中。您可以使用 [environment(_:_:)](View/environment.zh-Hans.md) 或 [environment(_:)](View/environment.zh-Hans.md) 修饰符，并传入模型数据，将数据添加到环境中。

在使用 [environment(_:_:)](View/environment.zh-Hans.md) 修饰符之前，您需要创建一个自定义的 [EnvironmentKey](EnvironmentKey.zh-Hans.md)。然后扩展 [EnvironmentValues](EnvironmentValues.zh-Hans.md)，使其包含一个自定义环境属性，该属性用于获取和设置自定义键的值。例如，以下代码为 `library` 创建了一个环境键和属性：

```swift
extension EnvironmentValues {
    var library: Library {
        get { self[LibraryKey.self] }
        set { self[LibraryKey.self] = newValue }
    }
}

private struct LibraryKey: EnvironmentKey {
    static let defaultValue: Library = Library()
}
```

有了自定义环境键和属性，视图就可以将模型数据添加到其环境中。例如，`LibraryView` 使用 [environment(_:_:)](View/environment.zh-Hans.md) 修饰符将 `Library` 实例的真实数据源添加到其环境中：

```swift
@main
struct BookReaderApp: App {
    @State private var library = Library()
    
    var body: some Scene {
        WindowGroup {
            LibraryView()
                .environment(\.library, library)
        }
    }
}
```

要从环境中检索 `Library` 实例，视图需要定义一个存储实例引用的局部变量，然后使用 [Environment](Environment.zh-Hans.md) 属性包装器包装该变量，并将指向自定义环境值的键路径传递给它。

```swift
struct LibraryView: View {
    @Environment(\.library) private var library

    var body: some View {
        // ...
    }
}
```

您还可以使用 [environment(_:)](View/environment.zh-Hans.md) 修饰符将模型数据直接存储在环境中，而无需定义自定义环境值。例如，以下代码使用此修饰符将 `Library` 实例添加到环境中：

```swift
@main
struct BookReaderApp: App {
    @State private var library = Library()
    
    var body: some Scene {
        WindowGroup {
            LibraryView()
                .environment(library)
        }
    }
}
```

要从环境中检索实例，另一个视图定义了一个局部变量来存储该实例，并使用 [Environment](Environment.zh-Hans.md) 属性包装器将其包装起来。但是，您可以提供模型数据类型，而不是提供指向环境值的键路径，如下面的代码所示：

```swift
struct LibraryView: View {
    @Environment(Library.self) private var library
    
    var body: some View {
        // ...
    }
}
```

默认情况下，当使用对象类型作为键时，从环境中读取对象会返回一个非可选对象。此默认行为假定当前层次结构中的某个视图之前已使用 [environment(_:)](View/environment.zh-Hans.md) 修饰符存储了该类型的非可选实例。如果视图尝试使用其类型检索对象，但该对象不在环境中，SwiftUI 将抛出异常。

如果无法保证某个对象存在于环境中，则可检索该对象的可选版本，如下面的代码所示。如果该对象在环境中不可用，SwiftUI 将返回 `nil` 而不是抛出异常。

```swift
@Environment(Library.self) private var library: Library?
```

### 在视图中更改模型数据

在大多数应用中，用户可以更改应用显示的数据。当数据更改时，任何显示该数据的视图都应更新以反映更改后的数据。借助 SwiftUI 中的 Observation，视图无需使用属性包装器或绑定即可支持数据更改。例如，以下代码在按钮的 action 闭包中切换书籍的 `isAvailable` 属性：

```swift
struct BookView: View {
    var book: Book
    
    var body: some View {
        List {
            Text(book.title)
            HStack {
                Text(book.isAvailable ? "Available for checkout" : "Waiting for return")
                Spacer()
                Button(book.isAvailable ? "Check out" : "Return") {
                    book.isAvailable.toggle()
                }
            }
        }
    }
}
```

但是，有时视图可能需要绑定才能更改可变属性的值。要提供绑定，请使用 [Bindable](Bindable.zh-Hans.md) 属性包装器包装模型数据。例如，以下代码使用 `@Bindable` 包装 `book` 变量。然后，它使用 [TextField](TextField.zh-Hans.md) 更改书籍的 `title` 属性，并使用 [Toggle](Toggle.zh-Hans.md) 更改 `isAvailable` 属性，同时使用 `$` 语法将绑定传递给每个属性。

```swift
struct BookEditView: View {
    @Bindable var book: Book
    @Environment(\.dismiss) private var dismiss
    
    var body: some View {
        VStack() {
            HStack {
                Text("Title")
                TextField("Title", text: $book.title)
                    .textFieldStyle(.roundedBorder)
                    .onSubmit {
                        dismiss()
                    }
            }
            
            Toggle(isOn: $book.isAvailable) {
                Text("Book is available")
            }
            
            Button("Close") {
                dismiss()
            }
            .buttonStyle(.borderedProminent)
        }
        .padding()
    }
}
```

您可以将 [Bindable](Bindable.zh-Hans.md) 属性包装器用于 [doc://com.apple.documentation/documentation/Observation/Observable] 对象的属性和变量。这包括全局变量、SwiftUI 类型之外的属性，甚至局部变量。例如，您可以在视图的 DL_0070 中创建变量 IC_0024：

CB_0020

变量 IC_0023 提供了一个绑定，将 DL_0069 连接到书籍的 IC_0021 属性，以便用户可以直接修改模型数据。

## 创建模型数据

- **从 Observable Object 协议迁移到 Observable 宏**：更新现有应用，以利用 Swift 中 Observation 的优势。

- SY_0102：定义并实现 Observable 协议的一致性。

- **监控应用中的数据变更**：使用可观察对象在应用的用户界面中显示数据变更。

- **StateObject**：一种属性包装器类型，用于实例化可观察对象。

- **ObservedObject**：一种属性包装器类型，用于订阅可观察对象，并在可观察对象变更时使视图失效。

- **ObservableObject**：一种带有发布者的对象类型，该发布者会在对象变更之前发出事件。


---
source: https://developer.apple.com/documentation/swiftui/managing-model-data-in-your-app
crawled: 2025-12-04T18:54:30Z
---

# Managing model data in your app

**Sample Code**

Create connections between your app’s data model and views.

## Overview

A SwiftUI app can display data that people can change using the app’s user interface (UI). To manage that data, an app creates a data model, which is a custom type that represents the data. A data model provides separation between the data and the views that interact with the data. This separation promotes modularity, improves testability, and helps make it easier to reason about how the app works.

Keeping the model data (that is, an instance of a data model) in sync with what appears on the screen can be challenging, especially when the data appears in multiple views of the UI at the same time.

SwiftUI helps keep your app’s UI up to date with changes made to the data thanks to Observation. With [doc://com.apple.documentation/documentation/Observation], a view in SwiftUI can form dependencies on observable data models and update the UI when data changes.



### Make model data observable

To make data changes visible to SwiftUI, apply the [doc://com.apple.documentation/documentation/Observation/Observable()] macro to your data model. This macro generates code that adds observation support to your data model at compile time, keeping your data model code focused on the properties that store data. For example, the following code defines a data model for books:

```swift
@Observable class Book: Identifiable {
    var title = "Sample Book Title"
    var author = Author()
    var isAvailable = true
}
```



### Observe model data in a view

In SwiftUI, a view forms a dependency on an observable data model object, such as an instance of `Book`, when the view’s [body-8kl5o](View/body-8kl5o.zh-Hans.md) property reads a property of the object. If `body` doesn’t read any properties of an observable data model object, the view doesn’t track any dependencies.

When a tracked property changes, SwiftUI updates the view. If other properties change that [body-8kl5o](View/body-8kl5o.zh-Hans.md) doesn’t read, the view is unaffected and avoids unnecessary updates. For example, the view in the following code updates only when a book’s `title` changes but not when `author` or `isAvailable` changes:

```swift
struct BookView: View {
    var book: Book
    
    var body: some View {
        Text(book.title)
    }
}
```

SwiftUI establishes this dependency tracking even if the view doesn’t store the observable type, such as when using a global property or singleton:

```swift
var globalBook: Book = Book()

struct BookView: View {
    var body: some View {
        Text(globalBook.title)
    }
}
```

Observation also supports tracking of computed properties when the computed property makes use of an observable property. For instance, the view in the following code updates when the number of available books changes:

```swift
@Observable class Library {
    var books: [Book] = [Book(), Book(), Book()]
    
    var availableBooksCount: Int {
        books.filter(\.isAvailable).count
    }
}

struct LibraryView: View {
    @Environment(Library.self) private var library
    
    var body: some View {
        NavigationStack {
            List(library.books) { book in
                // ...
            }
            .navigationTitle("Books available: \(library.availableBooksCount)")
        }
    }
}
```

When a view forms a dependency on a collection of objects, of any collection type, the view tracks changes made to the collection itself. For instance, the view in the following code forms a dependency on `books` because `body` reads it. As changes occur to `books`, such as inserting, deleting, moving, or replacing items in the collection, SwiftUI updates the view.

```swift
struct LibraryView: View {
    @State private var books = [Book(), Book(), Book()]

    var body: some View {
        List(books) { book in 
            Text(book.title)
        }
    }
}
```

However, `LibraryView` doesn’t form a dependency on the property `title` because the view’s [body-8kl5o](View/body-8kl5o.zh-Hans.md) doesn’t read it directly. The view stores the [List](List.zh-Hans.md) content closure as an `@escaping` closure that SwiftUI calls when lazily creating list items before they appear on the screen. This means that instead of `LibraryView` depending on a book’s `title`, each [Text](Text.zh-Hans.md) item of the list depends on `title`. Any changes to a `title` updates only the individual [Text](Text.zh-Hans.md) representing the book and not the others.



You can also share an observable model data object with another view. The receiving view forms a dependency if it reads any properties of the object in its [body-8kl5o](View/body-8kl5o.zh-Hans.md). For example, in the following code `LibraryView` shares an instance of `Book` with `BookView`, and `BookView` displays the book’s `title`. If the book’s `title` changes, SwiftUI updates only `BookView`, and not `LibraryView`, because only `BookView` reads the `title` property.

```swift
struct LibraryView: View {
    @State private var books = [Book(), Book(), Book()]

    var body: some View {
        List(books) { book in 
            BookView(book: book)
        }
    }
}

struct BookView: View {
    var book: Book
    
    var body: some View {
        Text(book.title)
    }
}
```

If a view doesn’t have any dependencies, SwiftUI doesn’t update the view when data changes. This approach allows an observable model data object to pass through multiple layers of a view hierarchy without each intermediate view forming a dependency.

```swift
// Will not update when any property of `book` changes.
struct LibraryView: View {
    @State private var books = [Book(), Book(), Book()]
    
    var body: some View {
        LibraryItemView(book: book)
    }
}

// Will not update when any property of `book` changes.
struct LibraryItemView: View {
    var book: Book
    
    var body: some View {
        BookView(book: book)
    }
}

// Will update when `book.title` changes.
struct BookView: View {
    var book: Book
    
    var body: some View {
        Text(book.title)
    }
}
```

However, a view that stores a reference to the observable object updates if the reference changes. This happens because the stored reference is part of the view’s value and not because the object is observable. For example, if the reference to book in the following code changes, SwiftUI updates the view:

```swift
struct BookView: View {
    var book: Book
    
    var body: some View {
        // ...
    }
}
```

A view can also form a dependency on an observable data model object accessed through another object. For example, the view in the following code updates when the author’s `name` changes:

```swift
struct LibraryItemView: View {
    var book: Book
    
    var body: some View {
        VStack(alignment: .leading) {
            Text(book.title)
            Text("Written by: \(book.author.name)")
                .font(.caption)
        }
    }
}
```

### Create the source of truth for model data

To create and store the source of truth for model data, declare a private variable and initialize it with a instance of an observable data model type. Then wrap it with a [State](State.zh-Hans.md) property wrapper. For example, the following code stores an instance of the data model type `Book` in the state variable `book`:

```swift
struct BookView: View {
    @State private var book = Book()
    
    var body: some View {
        Text(book.title)
    }
}
```

By wrapping the book with [State](State.zh-Hans.md), you’re telling SwiftUI to manage the storage of the instance. Each time SwiftUI re-creates `BookView`, it connects the `book` variable to the managed instance, providing the view a single source of truth for the model data.

You can also create a state object in your top-level [App](App.zh-Hans.md) instance or in one of your app’s [Scene](Scene.zh-Hans.md) instances. For example, the following code creates an instance of `Library` in the app’s top-level structure:

```swift
@main
struct BookReaderApp: App {
    @State private var library = Library()
    
    var body: some Scene {
        WindowGroup {
            LibraryView()
                .environment(library)
        }
    }
}
```

### Share model data throughout a view hierarchy

If you have a data model object, like `Library`, that you want to share throughout your app, you can either:

- pass the data model object to each view in the view hierarchy; or
- add the data model object to the view’s environment

Passing model data to each view is convenient when you have a shallow view hierarchy; for example, when a view doesn’t share the object with its subviews. However, you usually don’t know if a view needs to pass the object to subviews, and you may not know if a subview deep inside the layers of the hierarchy needs the model data.

To share model data throughout a view hierarchy without needing to pass it to each view, add the model data to the view’s environment. You can add the data to the environment using either [environment(_:_:)](View/environment.zh-Hans.md) or the [environment(_:)](View/environment.zh-Hans.md) modifier, passing in the model data.

Before you can use the [environment(_:_:)](View/environment.zh-Hans.md) modifier, you need to create a custom [EnvironmentKey](EnvironmentKey.zh-Hans.md). Then extend [EnvironmentValues](EnvironmentValues.zh-Hans.md) to include a custom environment property that gets and sets the value for the custom key. For instance, the following code creates an environment key and property for `library`:

```swift
extension EnvironmentValues {
    var library: Library {
        get { self[LibraryKey.self] }
        set { self[LibraryKey.self] = newValue }
    }
}

private struct LibraryKey: EnvironmentKey {
    static let defaultValue: Library = Library()
}
```

With the custom environment key and property in place, a view can add model data to its environment. For example, `LibraryView` adds the source of truth for a `Library` instance to its environment using the [environment(_:_:)](View/environment.zh-Hans.md) modifier:

```swift
@main
struct BookReaderApp: App {
    @State private var library = Library()
    
    var body: some Scene {
        WindowGroup {
            LibraryView()
                .environment(\.library, library)
        }
    }
}
```

To retrieve the `Library` instance from the environment, a view defines a local variable that stores a reference to the instance, and then wraps the variable with the [Environment](Environment.zh-Hans.md) property wrapper, passing in the key path to the custom environment value.

```swift
struct LibraryView: View {
    @Environment(\.library) private var library

    var body: some View {
        // ...
    }
}
```

You can also store model data directly in the environment without defining a custom environment value by using the [environment(_:)](View/environment.zh-Hans.md) modifier. For instance, the following code adds a `Library` instance to the environment using this modifier:

```swift
@main
struct BookReaderApp: App {
    @State private var library = Library()
    
    var body: some Scene {
        WindowGroup {
            LibraryView()
                .environment(library)
        }
    }
}
```

To retrieve the instance from the environment, another view defines a local variable to store the instance and wraps it with the [Environment](Environment.zh-Hans.md) property wrapper. But instead of providing a key path to the environment value, you can provide the model data type, as shown in the following code:

```swift
struct LibraryView: View {
    @Environment(Library.self) private var library
    
    var body: some View {
        // ...
    }
}
```

By default, reading an object from the environment returns a non-optional object when using the object type as the key. This default behavior assumes that a view in the current hierarchy previously stored a non-optional instance of the type using the [environment(_:)](View/environment.zh-Hans.md) modifier. If a view attempts to retrieve an object using its type and that object isn’t in the environment, SwiftUI throws exception.

In cases where there is no guarantee that an object is in the environment, retrieve an optional version of the object as shown in the following code. If the object isn’t available the environment, SwiftUI returns `nil` instead of throwing an exception.

```swift
@Environment(Library.self) private var library: Library?
```

### Change model data in a view

In most apps, people can change data that the app presents. When data changes, any views that display the data should update to reflect the changed data. With Observation in SwiftUI, a view can support data changes without using property wrappers or bindings. For example, the following toggles the `isAvailable` property of a book in the action closure of a button:

```swift
struct BookView: View {
    var book: Book
    
    var body: some View {
        List {
            Text(book.title)
            HStack {
                Text(book.isAvailable ? "Available for checkout" : "Waiting for return")
                Spacer()
                Button(book.isAvailable ? "Check out" : "Return") {
                    book.isAvailable.toggle()
                }
            }
        }
    }
}
```

However, there may be times when a view expects a binding before it can change the value of a mutable property. To provide a binding, wrap the model data with the [Bindable](Bindable.zh-Hans.md) property wrapper. For example, the following code wraps the `book` variable with `@Bindable`. Then it uses a [TextField](TextField.zh-Hans.md) to change the `title` property of a book, and a [Toggle](Toggle.zh-Hans.md) to change the `isAvailable` property, using the `$` syntax to pass a binding to each property.

```swift
struct BookEditView: View {
    @Bindable var book: Book
    @Environment(\.dismiss) private var dismiss
    
    var body: some View {
        VStack() {
            HStack {
                Text("Title")
                TextField("Title", text: $book.title)
                    .textFieldStyle(.roundedBorder)
                    .onSubmit {
                        dismiss()
                    }
            }
            
            Toggle(isOn: $book.isAvailable) {
                Text("Book is available")
            }
            
            Button("Close") {
                dismiss()
            }
            .buttonStyle(.borderedProminent)
        }
        .padding()
    }
}
```

You can use the [Bindable](Bindable.zh-Hans.md) property wrapper on properties and variables to an [doc://com.apple.documentation/documentation/Observation/Observable] object. This includes global variables, properties that exist outside of SwiftUI types, or even local variables. For example, you can create a `@Bindable` variable within a view’s [body-8kl5o](View/body-8kl5o.zh-Hans.md):

```swift
struct LibraryView: View {
    @State private var books = [Book(), Book(), Book()]

    var body: some View {
        List(books) { book in 
            @Bindable var book = book
            TextField("Title", text: $book.title)
        }
    }
}
```

The `@Bindable` variable `book` provides a binding that connects [TextField](TextField.zh-Hans.md) to the `title` property of a book so that a person can make changes directly to the model data.

## Creating model data

- **Migrating from the Observable Object protocol to the Observable macro**: Update your existing app to leverage the benefits of Observation in Swift.
- **Observable()**: Defines and implements conformance of the Observable protocol.
- **Monitoring data changes in your app**: Show changes to data in your app’s user interface by using observable objects.
- **StateObject**: A property wrapper type that instantiates an observable object.
- **ObservedObject**: A property wrapper type that subscribes to an observable object and invalidates a view whenever the observable object changes.
- **ObservableObject**: A type of object with a publisher that emits before the object has changed.

