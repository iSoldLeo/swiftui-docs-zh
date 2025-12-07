---
来源： https://developer.apple.com/documentation/SwiftUI/Bindable
抓取时间： 2025-12-02T17:32:11Z
---

# 可绑定

**Structure**

一种属性包装器类型，支持为可观察对象的可变属性创建绑定。

## 声明

```swift
@dynamicMemberLookup @propertyWrapper struct Bindable<Value>
```

## 概览

使用此属性包装器可创建与符合[doc://com.apple.documentation/documentation/Observation/Observable] 协议的数据模型对象的可变属性的绑定。例如，下面的代码用`book` 输入包装了`@Bindable`。然后，它使用[TextField](TextField.zh-Hans.md) 来更改书籍的`title` 属性，使用[Toggle](Toggle.zh-Hans.md) 来更改`isAvailable` 属性，使用`$` 语法将每个属性的绑定传递给这些控件。

```swift
@Observable
class Book: Identifiable {
    var title = "Sample Book Title"
    var isAvailable = true
}

struct BookEditView: View {
    @Bindable var book: Book
    @Environment(\.dismiss) private var dismiss

    var body: some View {
        Form {
            TextField("Title", text: $book.title)

            Toggle("Book is available", isOn: $book.isAvailable)

            Button("Close") {
                dismiss()
            }
        }
    }
}
```

您可以在[doc://com.apple.documentation/documentation/Observation/Observable] 对象的属性和变量上使用`Bindable` 属性包装器。这包括全局变量、存在于 SwiftUI 类型之外的属性，甚至局部变量。例如，您可以在视图的[body-8kl5o](View/body-8kl5o.zh-Hans.md)中创建一个`@Bindable`变量：

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

`@Bindable`变量`book`提供了一个绑定，将[TextField](TextField.zh-Hans.md)连接到书籍的`title`属性，以便用户可以直接更改模型数据。

当您需要绑定到存储在视图环境中的可观察对象的属性时，也可以使用这种方法。例如，下面的代码使用[Environment](Environment.zh-Hans.md) 属性包装器检索了一个可观察类型`Book` 的实例。然后，代码使用 `title` 语法创建一个 `@Bindable` 变量 `book`，并将`title` 属性的绑定传递给[TextField](TextField.zh-Hans.md)。

```swift
struct TitleEditView: View {
    @Environment(Book.self) private var book

    var body: some View {
        @Bindable var book = book
        TextField("Title", text: $book.title)
    }
}
```

## 创建可绑定值

- **init(_:)**：从一个可观察对象创建一个可绑定对象。
- **init(wrappedValue:)**：从可观察对象创建可绑定对象。
- **init(projectedValue:)**：从另一个可绑定对象的值创建一个可绑定对象。

## 获取值

- **wrappedValue**：被包装的对象。
- **projectedValue**：对象的可绑定包装器，可使用动态成员查找功能为其属性创建绑定。
- **subscript(dynamicMember:)**：返回与给定键路径值的绑定。

## 创建和共享视图状态

- 管理用户界面状态**：在应用程序的视图层次结构中封装特定于视图的数据，使视图可重复使用。
- **State**：一种属性封装类型，可读写由 SwiftUI 管理的值。
- **Binding**：一种属性包装器类型，可以读写由真相源拥有的值。

## 符合

- 可复制
- 可识别
- 可发送
- 可发送元数据类型


---
source: https://developer.apple.com/documentation/SwiftUI/Bindable
crawled: 2025-12-02T17:32:11Z
---

# Bindable

**Structure**

A property wrapper type that supports creating bindings to the mutable properties of observable objects.

## Declaration

```swift
@dynamicMemberLookup @propertyWrapper struct Bindable<Value>
```

## Overview

Use this property wrapper to create bindings to mutable properties of a data model object that conforms to the [doc://com.apple.documentation/documentation/Observation/Observable] protocol. For example, the following code wraps the `book` input with `@Bindable`. Then it uses a [TextField](TextField.zh-Hans.md) to change the `title` property of a book, and a [Toggle](Toggle.zh-Hans.md) to change the `isAvailable` property, using the `$` syntax to pass a binding for each property to those controls.

```swift
@Observable
class Book: Identifiable {
    var title = "Sample Book Title"
    var isAvailable = true
}

struct BookEditView: View {
    @Bindable var book: Book
    @Environment(\.dismiss) private var dismiss

    var body: some View {
        Form {
            TextField("Title", text: $book.title)

            Toggle("Book is available", isOn: $book.isAvailable)

            Button("Close") {
                dismiss()
            }
        }
    }
}
```

You can use the `Bindable` property wrapper on properties and variables to an [doc://com.apple.documentation/documentation/Observation/Observable] object. This includes global variables, properties that exists outside of SwiftUI types, or even local variables. For example, you can create a `@Bindable` variable within a view’s [body-8kl5o](View/body-8kl5o.zh-Hans.md):

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

Use this same approach when you need a binding to a property of an observable object stored in a view’s environment. For example, the following code uses the [Environment](Environment.zh-Hans.md) property wrapper to retrieve an instance of the observable type `Book`. Then the code creates a `@Bindable` variable `book` and passes a binding for the `title` property to a [TextField](TextField.zh-Hans.md) using the `$` syntax.

```swift
struct TitleEditView: View {
    @Environment(Book.self) private var book

    var body: some View {
        @Bindable var book = book
        TextField("Title", text: $book.title)
    }
}
```

## Creating a bindable value

- **init(_:)**: Creates a bindable object from an observable object.
- **init(wrappedValue:)**: Creates a bindable object from an observable object.
- **init(projectedValue:)**: Creates a bindable from the value of another bindable.

## Getting the value

- **wrappedValue**: The wrapped object.
- **projectedValue**: The bindable wrapper for the object that creates bindings to its properties using dynamic member lookup.
- **subscript(dynamicMember:)**: Returns a binding to the value of a given key path.

## Creating and sharing view state

- **Managing user interface state**: Encapsulate view-specific data within your app’s view hierarchy to make your views reusable.
- **State**: A property wrapper type that can read and write a value managed by SwiftUI.
- **Binding**: A property wrapper type that can read and write a value owned by a source of truth.

## Conforms To

- Copyable
- Identifiable
- Sendable
- SendableMetatype

