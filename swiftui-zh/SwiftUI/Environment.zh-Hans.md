---
来源： https://developer.apple.com/documentation/SwiftUI/Environment
抓取时间： 2025-12-02T17:32:20Z
---

# 环境

**Structure**

从视图环境中读取值的属性包装器。

## 声明

```swift
@frozen @propertyWrapper struct Environment<Value>
```

## 概览

使用`Environment` 属性包装器读取存储在视图环境中的值。在属性声明中使用[EnvironmentValues](EnvironmentValues.zh-Hans.md)键路径指明要读取的值。例如，可以创建一个属性，使用[colorScheme](EnvironmentValues/colorScheme.zh-Hans.md) 属性的关键路径读取当前视图的配色方案：

```swift
@Environment(\.colorScheme) var colorScheme: ColorScheme
```

您可以根据关联的值作为视图内容的条件，该值是从所声明属性的[wrappedValue](Environment/wrappedValue.zh-Hans.md)中读取的。与任何属性包装器一样，您可以通过直接引用属性来访问包装后的值：

```swift
if colorScheme == .dark { // Checks the wrapped value.
    DarkContent()
} else {
    LightContent()
}
```

如果值发生变化，SwiftUI 会更新视图中依赖于该值的任何部分。例如，在上面的示例中，如果用户更改了外观设置，就可能发生这种情况。

您可以使用此属性包装器读取（但不设置）环境值。SwiftUI 会根据系统设置自动更新某些环境值，并为其他环境值提供合理的默认值。您可以使用[environment(_:_:)](View/environment.zh-Hans.md)视图修饰符覆盖其中一些值，也可以设置自己定义的自定义环境值。

有关 SwiftUI 提供的环境值的完整列表，请参阅 [EnvironmentValues](EnvironmentValues.zh-Hans.md) 结构的属性。有关创建自定义环境值的信息，请参阅 [Entry()](Entry.zh-Hans.md) 宏。

### 获取可观察对象

也可以使用 `Environment` 从视图的环境中获取可观察对象。可观察对象必须符合[doc://com.apple.documentation/documentation/Observation/Observable] 协议，而且您的应用程序必须使用对象本身或关键路径在环境中设置该对象。

要使用对象本身在环境中设置对象，请使用[environment(_:)](View/environment.zh-Hans.md)修饰符：

```swift
@Observable
class Library {
    var books: [Book] = [Book(), Book(), Book()]

    var availableBooksCount: Int {
        books.filter(\.isAvailable).count
    }
}

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
```修饰符。

要使用可观察对象的类型获取该对象，请创建一个属性并提供对象类型的 `Environment` 属性包装器：

```swift
struct LibraryView: View {
    @Environment(Library.self) private var library

    var body: some View {
        // ...
    }
}
```

默认情况下，当使用对象类型作为键时，从环境中读取对象会返回一个非选项对象。这种默认行为假定当前层次结构中的视图以前使用[environment(_:)](View/environment.zh-Hans.md)修饰符存储了该类型的非可选实例。如果视图尝试使用其类型检索对象，而该对象不在环境中，SwiftUI 将抛出异常。

在无法保证对象是否在环境中的情况下，可检索对象的可选版本，如下代码所示。如果环境中没有该对象，SwiftUI 将返回 `nil`，而不是抛出异常。

```swift
@Environment(Library.self) private var library: Library?
```

### 使用关键路径获取可观察对象

要使用关键路径设置对象，请使用 [environment(_:_:)](View/environment.zh-Hans.md) 修饰符：

```swift
@Observable
class Library {
    var books: [Book] = [Book(), Book(), Book()]

    var availableBooksCount: Int {
        books.filter(\.isAvailable).count
    }
}

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
```修饰符

要获取对象，请创建一个属性并指定键路径：

```swift
struct LibraryView: View {
    @Environment(\.library) private var library

    var body: some View {
        // ...
    }
}
```

## 创建环境实例

- **init(_:)**：创建环境属性以读取指定的键路径。

## 获取值

- **wrappedValue**：环境属性的当前值。

## 访问环境值

- **EnvironmentValues**：通过视图层次结构传播的环境值集合。

## 符合

- 动态属性
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/Environment
crawled: 2025-12-02T17:32:20Z
---

# Environment

**Structure**

A property wrapper that reads a value from a view’s environment.

## Declaration

```swift
@frozen @propertyWrapper struct Environment<Value>
```

## Overview

Use the `Environment` property wrapper to read a value stored in a view’s environment. Indicate the value to read using an [EnvironmentValues](EnvironmentValues.zh-Hans.md) key path in the property declaration. For example, you can create a property that reads the color scheme of the current view using the key path of the [colorScheme](EnvironmentValues/colorScheme.zh-Hans.md) property:

```swift
@Environment(\.colorScheme) var colorScheme: ColorScheme
```

You can condition a view’s content on the associated value, which you read from the declared property’s [wrappedValue](Environment/wrappedValue.zh-Hans.md). As with any property wrapper, you access the wrapped value by directly referring to the property:

```swift
if colorScheme == .dark { // Checks the wrapped value.
    DarkContent()
} else {
    LightContent()
}
```

If the value changes, SwiftUI updates any parts of your view that depend on the value. For example, that might happen in the above example if the user changes the Appearance settings.

You can use this property wrapper to read — but not set — an environment value. SwiftUI updates some environment values automatically based on system settings and provides reasonable defaults for others. You can override some of these, as well as set custom environment values that you define, using the [environment(_:_:)](View/environment.zh-Hans.md) view modifier.

For the complete list of environment values SwiftUI provides, see the properties of the [EnvironmentValues](EnvironmentValues.zh-Hans.md) structure. For information about creating custom environment values, see the [Entry()](Entry.zh-Hans.md) macro.

### Get an observable object

You can also use `Environment` to get an observable object from a view’s environment. The observable object must conform to the [doc://com.apple.documentation/documentation/Observation/Observable] protocol, and your app must set the object in the environment using the object itself or a key path.

To set the object in the environment using the object itself, use the [environment(_:)](View/environment.zh-Hans.md) modifier:

```swift
@Observable
class Library {
    var books: [Book] = [Book(), Book(), Book()]

    var availableBooksCount: Int {
        books.filter(\.isAvailable).count
    }
}

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

To get the observable object using its type, create a property and provide the `Environment` property wrapper the object’s type:

```swift
struct LibraryView: View {
    @Environment(Library.self) private var library

    var body: some View {
        // ...
    }
}
```

By default, reading an object from the environment returns a non-optional object when using the object type as the key. This default behavior assumes that a view in the current hierarchy previously stored a non-optional instance of the type using the [environment(_:)](View/environment.zh-Hans.md) modifier. If a view attempts to retrieve an object using its type and that object isn’t in the environment, SwiftUI throws an exception.

In cases where there is no guarantee that an object is in the environment, retrieve an optional version of the object as shown in the following code. If the object isn’t available the environment, SwiftUI returns `nil` instead of throwing an exception.

```swift
@Environment(Library.self) private var library: Library?
```

### Get an observable object using a key path

To set the object with a key path, use the [environment(_:_:)](View/environment.zh-Hans.md) modifier:

```swift
@Observable
class Library {
    var books: [Book] = [Book(), Book(), Book()]

    var availableBooksCount: Int {
        books.filter(\.isAvailable).count
    }
}

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

To get the object, create a property and specify the key path:

```swift
struct LibraryView: View {
    @Environment(\.library) private var library

    var body: some View {
        // ...
    }
}
```

## Creating an environment instance

- **init(_:)**: Creates an environment property to read the specified key path.

## Getting the value

- **wrappedValue**: The current value of the environment property.

## Accessing environment values

- **EnvironmentValues**: A collection of environment values propagated through a view hierarchy.

## Conforms To

- DynamicProperty
- Sendable
- SendableMetatype

