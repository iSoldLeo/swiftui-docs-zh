--- 来源：https://developer.apple.com/documentation/SwiftUI/State

抓取时间：2025-12-02T17:32:10Z

---

# State

**Structure**

一种属性包装类型，可以读取和写入由 SwiftUI 管理的值。

## 声明

```swift
@frozen @propertyWrapper struct State<Value>
```

## 概述

将 state 用作存储在视图层次结构中的给定值类型的唯一数据源。通过将 `@State` 特性应用于属性声明并提供初始值，即可在 [App](App.zh-Hans.md)、[Scene](Scene.zh-Hans.md) 或 [View](View.zh-Hans.md) 中创建 state 值。将状态声明为私有，以避免在成员初始化器中设置状态，这可能会与 SwiftUI 提供的存储管理机制冲突：

```swift
struct PlayButton: View {
    @State private var isPlaying: Bool = false // Create the state.

    var body: some View {
        Button(isPlaying ? "Pause" : "Play") { // Read the state.
            isPlaying.toggle() // Write the state.
        }
    }
}
```

SwiftUI 管理属性的存储。当值发生变化时，SwiftUI 会更新依赖于该值的视图层次结构部分。要访问状态的底层值，可以使用其 [wrappedValue](State/wrappedValue.zh-Hans.md) 属性。但是，Swift 提供了一种快捷方式，允许您通过直接引用状态实例来访问包装后的值。上面的示例通过直接引用属性来读取和写入 `isPlaying` 状态属性的包装值。

在需要访问该值的视图层次结构中的最高层视图中，将状态声明为私有。然后，将状态共享给任何也需要访问的子视图，可以直接共享以实现只读访问，也可以通过绑定来实现读写访问。您可以从任何线程安全地修改状态属性。

### 与子视图共享状态

如果将状态属性传递给子视图，SwiftUI 会在容器视图中的值发生变化时更新子视图，但子视图无法修改该值。要使子视图能够修改状态中存储的值，请改为传递 [Binding](Binding.zh-Hans.md)。

例如，您可以从上面的示例中移除播放按钮的 `isPlaying` 状态，并改为让按钮绑定：

```swift
struct PlayButton: View {
    @Binding var isPlaying: Bool // Play button now receives a binding.

    var body: some View {
        Button(isPlaying ? "Pause" : "Play") {
            isPlaying.toggle()
        }
    }
}
```

然后，您可以定义一个播放器视图，该视图声明状态并创建与该状态的绑定。通过访问状态的 [projectedValue](State/projectedValue.zh-Hans.md) 获取状态值的绑定，该属性名可通过在属性名称前加上美元符号 (`$`) 获得：

```swift
struct PlayerView: View {
    @State private var isPlaying: Bool = false // Create the state here now.

    var body: some View {
        VStack {
            PlayButton(isPlaying: $isPlaying) // Pass a binding.

            // ...
        }
    }
}
```

与 [StateObject](StateObject.zh-Hans.md) 类似，将 `State` 声明为私有，以防止在成员初始化器中设置它，这可能会与 SwiftUI 提供的存储管理冲突。与状态对象不同，始终通过在状态声明中提供默认值来初始化状态，如上面的示例所示。状态仅用于视图及其子视图的本地存储。

### 存储可观察对象

您还可以将使用 [doc://com.apple.documentation/documentation/Observation/Observable()] 宏创建的可观察对象存储在 `State` 中；例如：

```swift
@Observable
class Library {
    var name = "My library of books"
    // ...
}

struct ContentView: View {
    @State private var library = Library()

    var body: some View {
        LibraryView(library: library)
    }
}
```

当 SwiftUI 实例化视图时，属性 `State` 总是会初始化其默认值。因此，在初始化默认值时，应避免产生副作用和执行性能密集型操作。例如，如果视图频繁更新，每次视图初始化时都分配一个新的默认对象可能会非常耗费资源。您可以改用 [task(priority:_:)](View/task_priority.zh-Hans.md) 修饰符来延迟对象的创建，该修饰符仅在视图首次出现时调用一次：

```swift
struct ContentView: View {
    @State private var library: Library?

    var body: some View {
        LibraryView(library: library)
            .task {
                library = Library()
            }
    }
}
```

延迟创建可观察状态对象可以确保每次 SwiftUI 初始化视图时都不会发生不必要的对象分配。使用 [task(priority:_:)](View/task_priority.zh-Hans.md) 修饰符也是延迟创建视图初始状态所需的任何其他操作（例如网络调用或文件访问）的有效方法。

### 与子视图共享可观察状态对象

要与子视图共享存储在 `State` 中的 [doc://com.apple.documentation/documentation/Observation/Observable] 对象，请将该对象引用传递给子视图。SwiftUI 会在对象的可观察属性发生更改时更新子视图，但仅当子视图的 [body-8kl5o](View/body-8kl5o.zh-Hans.md) 读取该属性时才会更新。例如，在以下代码中，`BookView` 会在 `title` 每次更改时更新，但不会随着 `isAvailable` 的更改而更新：

```swift
@Observable
class Book {
    var title = "A sample book"
    var isAvailable = true
}

struct ContentView: View {
    @State private var book = Book()

    var body: some View {
        BookView(book: book)
    }
}

struct BookView: View {
    var book: Book

    var body: some View {
        Text(book.title)
    }
}
```

`State` 属性提供对其值的绑定。存储对象时，您可以获取该对象的 [Binding](Binding.zh-Hans.md)，具体来说，是获取对该对象的引用。当您需要更改存储在其他子视图状态中的引用时，例如将引用设置为 `nil`，这将非常有用：

```swift
struct ContentView: View {
    @State private var book: Book?

    var body: some View {
        DeleteBookView(book: $book)
            .task {
                book = Book()
            }
    }
}

struct DeleteBookView: View {
    @Binding var book: Book?

    var body: some View {
        Button("Delete book") {
            book = nil
        }
    }
}
```

但是，当您需要更改存储在 `State` 中的对象的属性时，无需将 [Binding](Binding.zh-Hans.md) 传递给该对象。例如，您可以通过传递对象引用而不是绑定到该引用，在子视图中将对象的属性设置为新值：

```swift
struct ContentView: View {
    @State private var book = Book()

    var body: some View {
        BookCheckoutView(book: book)
    }
}

struct BookCheckoutView: View {
    var book: Book

    var body: some View {
        Button(book.isAvailable ? "Check out book" : "Return book") {
            book.isAvailable.toggle()
        }
    }
}
```

如果您需要绑定到对象的特定属性，您可以传递绑定到对象并在需要时提取到特定属性的绑定，或者传递对象引用并使用 [Bindable](Bindable.zh-Hans.md) 属性包装器创建到特定属性的绑定。例如，在以下代码中，`BookEditorView` 将 `book` 包装在 `@Bindable` 中。然后，视图使用 `$` 语法将绑定到 `title` 的值传递给 [TextField](TextField.zh-Hans.md)：

```swift
struct ContentView: View {
    @State private var book = Book()

    var body: some View {
        BookView(book: book)
    }
}

struct BookView: View {
    let book: Book

    var body: some View {
        BookEditorView(book: book)
    }
}

struct BookEditorView: View {
    @Bindable var book: Book

    var body: some View {
        TextField("Title", text: $book.title)
    }
}
```

## 创建状态

- **init(wrappedValue:)**：创建一个存储初始包装值的状态属性。

- **init(initialValue:)**：创建一个存储初始值的状态属性。

- **init()**：创建一个没有初始值的状态属性。

## 获取值

- **wrappedValue**：状态变量引用的底层值。

- **projectedValue**：状态值的绑定。

## 创建和共享视图状态

- **管理用户界面状态**：将视图特定数据封装在应用程序的视图层级结构中，使视图可重用。

- **Bindable**：支持创建与可观察对象可变属性绑定的属性包装器类型。

- **Binding**：可以读取和写入由数据源拥有的值的属性包装器类型。

## 符合以下规范

- DynamicProperty

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/State
crawled: 2025-12-02T17:32:10Z
---

# State

**Structure**

A property wrapper type that can read and write a value managed by SwiftUI.

## Declaration

```swift
@frozen @propertyWrapper struct State<Value>
```

## Overview

Use state as the single source of truth for a given value type that you store in a view hierarchy. Create a state value in an [App](App.zh-Hans.md), [Scene](Scene.zh-Hans.md), or [View](View.zh-Hans.md) by applying the `@State` attribute to a property declaration and providing an initial value. Declare state as private to prevent setting it in a memberwise initializer, which can conflict with the storage management that SwiftUI provides:

```swift
struct PlayButton: View {
    @State private var isPlaying: Bool = false // Create the state.

    var body: some View {
        Button(isPlaying ? "Pause" : "Play") { // Read the state.
            isPlaying.toggle() // Write the state.
        }
    }
}
```

SwiftUI manages the property’s storage. When the value changes, SwiftUI updates the parts of the view hierarchy that depend on the value. To access a state’s underlying value, you use its [wrappedValue](State/wrappedValue.zh-Hans.md) property. However, as a shortcut Swift enables you to access the wrapped value by referring directly to the state instance. The above example reads and writes the `isPlaying` state property’s wrapped value by referring to the property directly.

Declare state as private in the highest view in the view hierarchy that needs access to the value. Then share the state with any subviews that also need access, either directly for read-only access, or as a binding for read-write access. You can safely mutate state properties from any thread.

### Share state with subviews

If you pass a state property to a subview, SwiftUI updates the subview any time the value changes in the container view, but the subview can’t modify the value. To enable the subview to modify the state’s stored value, pass a [Binding](Binding.zh-Hans.md) instead.

For example, you can remove the `isPlaying` state from the play button in the above example, and instead make the button take a binding:

```swift
struct PlayButton: View {
    @Binding var isPlaying: Bool // Play button now receives a binding.

    var body: some View {
        Button(isPlaying ? "Pause" : "Play") {
            isPlaying.toggle()
        }
    }
}
```

Then you can define a player view that declares the state and creates a binding to the state. Get the binding to the state value by accessing the state’s [projectedValue](State/projectedValue.zh-Hans.md), which you get by prefixing the property name with a dollar sign (`$`):

```swift
struct PlayerView: View {
    @State private var isPlaying: Bool = false // Create the state here now.

    var body: some View {
        VStack {
            PlayButton(isPlaying: $isPlaying) // Pass a binding.

            // ...
        }
    }
}
```

Like you do for a [StateObject](StateObject.zh-Hans.md), declare `State` as private to prevent setting it in a memberwise initializer, which can conflict with the storage management that SwiftUI provides. Unlike a state object, always initialize state by providing a default value in the state’s declaration, as in the above examples. Use state only for storage that’s local to a view and its subviews.

### Store observable objects

You can also store observable objects that you create with the [doc://com.apple.documentation/documentation/Observation/Observable()] macro in `State`; for example:

```swift
@Observable
class Library {
    var name = "My library of books"
    // ...
}

struct ContentView: View {
    @State private var library = Library()

    var body: some View {
        LibraryView(library: library)
    }
}
```

A `State` property always instantiates its default value when SwiftUI instantiates the view. For this reason, avoid side effects and performance-intensive work when initializing the default value. For example, if a view updates frequently, allocating a new default object each time the view initializes can become expensive. Instead, you can defer the creation of the object using the [task(priority:_:)](View/task_priority.zh-Hans.md) modifier, which is called only once when the view first appears:

```swift
struct ContentView: View {
    @State private var library: Library?

    var body: some View {
        LibraryView(library: library)
            .task {
                library = Library()
            }
    }
}
```

Delaying the creation of the observable state object ensures that unnecessary allocations of the object doesn’t happen each time SwiftUI initializes the view. Using the [task(priority:_:)](View/task_priority.zh-Hans.md) modifier is also an effective way to defer any other kind of work required to create the initial state of the view, such as network calls or file access.



### Share observable state objects with subviews

To share an [doc://com.apple.documentation/documentation/Observation/Observable] object stored in `State` with a subview, pass the object reference to the subview. SwiftUI updates the subview anytime an observable property of the object changes, but only when the subview’s [body-8kl5o](View/body-8kl5o.zh-Hans.md) reads the property. For example, in the following code `BookView` updates each time `title` changes but not when `isAvailable` changes:

```swift
@Observable
class Book {
    var title = "A sample book"
    var isAvailable = true
}

struct ContentView: View {
    @State private var book = Book()

    var body: some View {
        BookView(book: book)
    }
}

struct BookView: View {
    var book: Book

    var body: some View {
        Text(book.title)
    }
}
```

`State` properties provide bindings to their value. When storing an object, you can get a [Binding](Binding.zh-Hans.md) to that object, specifically the reference to the object. This is useful when you need to change the reference stored in state in some other subview, such as setting the reference to `nil`:

```swift
struct ContentView: View {
    @State private var book: Book?

    var body: some View {
        DeleteBookView(book: $book)
            .task {
                book = Book()
            }
    }
}

struct DeleteBookView: View {
    @Binding var book: Book?

    var body: some View {
        Button("Delete book") {
            book = nil
        }
    }
}
```

However, passing a [Binding](Binding.zh-Hans.md) to an object stored in `State` isn’t necessary when you need to change properties of that object. For example, you can set the properties of the object to new values in a subview by passing the object reference instead of a binding to the reference:

```swift
struct ContentView: View {
    @State private var book = Book()

    var body: some View {
        BookCheckoutView(book: book)
    }
}

struct BookCheckoutView: View {
    var book: Book

    var body: some View {
        Button(book.isAvailable ? "Check out book" : "Return book") {
            book.isAvailable.toggle()
        }
    }
}
```

If you need a binding to a specific property of the object, pass either the binding to the object and extract bindings to specific properties where needed, or pass the object reference and use the [Bindable](Bindable.zh-Hans.md) property wrapper to create bindings to specific properties. For example, in the following code `BookEditorView` wraps `book` with `@Bindable`. Then the view uses the `$` syntax to pass to a [TextField](TextField.zh-Hans.md) a binding to `title`:

```swift
struct ContentView: View {
    @State private var book = Book()

    var body: some View {
        BookView(book: book)
    }
}

struct BookView: View {
    let book: Book

    var body: some View {
        BookEditorView(book: book)
    }
}

struct BookEditorView: View {
    @Bindable var book: Book

    var body: some View {
        TextField("Title", text: $book.title)
    }
}
```

## Creating a state

- **init(wrappedValue:)**: Creates a state property that stores an initial wrapped value.
- **init(initialValue:)**: Creates a state property that stores an initial value.
- **init()**: Creates a state property without an initial value.

## Getting the value

- **wrappedValue**: The underlying value referenced by the state variable.
- **projectedValue**: A binding to the state value.

## Creating and sharing view state

- **Managing user interface state**: Encapsulate view-specific data within your app’s view hierarchy to make your views reusable.
- **Bindable**: A property wrapper type that supports creating bindings to the mutable properties of observable objects.
- **Binding**: A property wrapper type that can read and write a value owned by a source of truth.

## Conforms To

- DynamicProperty
- Sendable
- SendableMetatype

