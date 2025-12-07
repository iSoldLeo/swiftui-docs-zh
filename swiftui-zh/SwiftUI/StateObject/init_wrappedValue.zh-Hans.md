--- 来源：https://developer.apple.com/documentation/SwiftUI/StateObject/init(wrappedValue:)

抓取时间：2025-12-02T21:00:19Z

---

# init(wrappedValue:)

**Initializer**

创建一个新的状态对象，并为其添加一个初始包装值。

## 声明

```swift
nonisolated init(wrappedValue thunk: @autoclosure @escaping () -> ObjectType)
```

## 参数

- **thunk**：状态对象的初始值。

## 说明

通常情况下，您不会直接调用此初始化器。相反，当您在 `[App](../App.zh-Hans.md)`、`[Scene](../Scene.zh-Hans.md)` 或 `[View](../View.zh-Hans.md)` 中声明带有 ``@StateObject`` 特性的属性并提供初始值时，SwiftUI 会自动调用它：

````swift
struct MyView: View {
    @StateObject private var model = DataModel()

    // ...
}
````

SwiftUI 只会为您声明的每个容器实例创建一个状态对象实例。在上面的代码中，SwiftUI 仅在首次初始化特定 ``MyView`` 实例时创建 ``model``。另一方面，每个 ``MyView`` 实例都会创建一个独立的数据模型实例。例如，以下 [VStack](../VStack.zh-Hans.md) 中的每个视图都有自己的模型存储：

```swift
var body: some View {
    VStack {
        MyView()
        MyView()
    }
}
```

### 使用外部数据初始化

如果状态对象的初始状态依赖于外部数据，您可以直接调用此初始化器。但是，这样做时请务必谨慎，因为即使您多次调用状态对象初始化器，SwiftUI 在视图的生命周期内也只会初始化对象一次，这可能会导致意外行为。有关更多信息和示例，请参阅 [StateObject](../StateObject.zh-Hans.md)。


---
source: https://developer.apple.com/documentation/SwiftUI/StateObject/init(wrappedValue:)
crawled: 2025-12-02T21:00:19Z
---

# init(wrappedValue:)

**Initializer**

Creates a new state object with an initial wrapped value.

## Declaration

```swift
nonisolated init(wrappedValue thunk: @autoclosure @escaping () -> ObjectType)
```

## Parameters

- **thunk**: An initial value for the state object.

## Discussion

You typically don’t call this initializer directly. Instead, SwiftUI calls it for you when you declare a property with the `@StateObject` attribute in an [App](../App.zh-Hans.md), [Scene](../Scene.zh-Hans.md), or [View](../View.zh-Hans.md) and provide an initial value:

```swift
struct MyView: View {
    @StateObject private var model = DataModel()

    // ...
}
```

SwiftUI creates only one instance of the state object for each container instance that you declare. In the above code, SwiftUI creates `model` only the first time it initializes a particular instance of `MyView`. On the other hand, each instance of `MyView` creates a distinct instance of the data model. For example, each of the views in the following [VStack](../VStack.zh-Hans.md) has its own model storage:

```swift
var body: some View {
    VStack {
        MyView()
        MyView()
    }
}
```

### Initialize using external data

If the initial state of a state object depends on external data, you can call this initializer directly. However, use caution when doing this, because SwiftUI only initializes the object once during the lifetime of the view — even if you call the state object initializer more than once — which might result in unexpected behavior. For more information and an example, see [StateObject](../StateObject.zh-Hans.md).

