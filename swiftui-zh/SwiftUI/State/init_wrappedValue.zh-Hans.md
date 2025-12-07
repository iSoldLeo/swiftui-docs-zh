---
来源： https://developer.apple.com/documentation/SwiftUI/State/init(wrappedValue:)
抓取时间： 2025-12-01T10:55:31Z
---

# init(wrappedValue:)

**Initializer**

创建一个存储初始包装值的状态属性。

## 声明

```swift
init(wrappedValue value: Value)
```

## 参数

- **value**：要存储在状态属性中的初始值。

## 讨论

您不会直接调用此初始化器。相反，当您使用 `@State` 属性声明属性并提供初始值时，SwiftUI 会为您调用它：

```swift
struct MyView: View {
    @State private var isPlaying: Bool = false

    // ...
}
```

对于您声明的每个容器实例，SwiftUI 只初始化状态存储一次。在上述代码中，SwiftUI 仅在第一次初始化`isPlaying` 的特定实例时创建`MyView`。另一方面，`MyView` 的每个实例都会创建一个不同的状态实例。例如，下面[VStack](../VStack.zh-Hans.md) 中的每个视图都有自己的`isPlaying` 值：

```swift
var body: some View {
    VStack {
        MyView()
        MyView()
    }
}
```

## 创建一个状态

- **init(initialValue:)**：创建一个存储初始值的状态属性。
- **init()**：创建没有初始值的状态属性。


---
source: https://developer.apple.com/documentation/SwiftUI/State/init(wrappedValue:)
crawled: 2025-12-01T10:55:31Z
---

# init(wrappedValue:)

**Initializer**

Creates a state property that stores an initial wrapped value.

## Declaration

```swift
init(wrappedValue value: Value)
```

## Parameters

- **value**: An initial value to store in the state property.

## Discussion

You don’t call this initializer directly. Instead, SwiftUI calls it for you when you declare a property with the `@State` attribute and provide an initial value:

```swift
struct MyView: View {
    @State private var isPlaying: Bool = false

    // ...
}
```

SwiftUI initializes the state’s storage only once for each container instance that you declare. In the above code, SwiftUI creates `isPlaying` only the first time it initializes a particular instance of `MyView`. On the other hand, each instance of `MyView` creates a distinct instance of the state. For example, each of the views in the following [VStack](../VStack.zh-Hans.md) has its own `isPlaying` value:

```swift
var body: some View {
    VStack {
        MyView()
        MyView()
    }
}
```

## Creating a state

- **init(initialValue:)**: Creates a state property that stores an initial value.
- **init()**: Creates a state property without an initial value.

