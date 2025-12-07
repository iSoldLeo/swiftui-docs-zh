--- 来源：https://developer.apple.com/documentation/SwiftUI/StateObject/projectedValue
抓取时间：2025-12-02T21:00:21Z

---

# projectedValue

**实例属性**

状态对象的投影，用于创建与其属性的绑定。

## 声明

```swift
@MainActor @preconcurrency var projectedValue: ObservedObject<ObjectType>.Wrapper { get }
```

## 说明

使用投影值可以获取状态对象属性的 [Binding](../Binding.zh-Hans.md)。要访问投影值，请在属性名称前加上美元符号 (`$`)。例如，您可以将模型的 `isEnabled` 布尔值绑定到 [Toggle](../Toggle.zh-Hans.md)，以便 ```swift
struct MyView: View {
    @StateObject private var model = DataModel()

    var body: some View {
        Toggle("Enabled", isOn: $model.isEnabled)
    }
}
``` 可以控制该值：

```swift
struct MyView: View {
    @StateObject private var model = DataModel()

    var body: some View {
        Toggle("Enabled", isOn: $model.isEnabled)
    }
}
```

## 获取值

- **wrappedValue**：状态对象引用的底层值。


---
source: https://developer.apple.com/documentation/SwiftUI/StateObject/projectedValue
crawled: 2025-12-02T21:00:21Z
---

# projectedValue

**Instance Property**

A projection of the state object that creates bindings to its properties.

## Declaration

```swift
@MainActor @preconcurrency var projectedValue: ObservedObject<ObjectType>.Wrapper { get }
```

## Discussion

Use the projected value to get a [Binding](../Binding.zh-Hans.md) to a property of a state object. To access the projected value, prefix the property name with a dollar sign (`$`). For example, you can get a binding to a model’s `isEnabled` Boolean so that a [Toggle](../Toggle.zh-Hans.md) can control the value:

```swift
struct MyView: View {
    @StateObject private var model = DataModel()

    var body: some View {
        Toggle("Enabled", isOn: $model.isEnabled)
    }
}
```



## Getting the value

- **wrappedValue**: The underlying value referenced by the state object.

