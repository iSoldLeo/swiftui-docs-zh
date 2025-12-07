---
来源： https://developer.apple.com/documentation/SwiftUI/ObservedObject/projectedValue
抓取时间： 2025-12-02T21:00:24Z
---

# 预计值

**实例属性**

观察对象的投影，用于创建与对象属性的绑定。

## 声明

```swift
@MainActor @preconcurrency var projectedValue: ObservedObject<ObjectType>.Wrapper { get }
```

## 讨论

使用预测值可以获得观测对象属性的[Binding](../Binding.zh-Hans.md)。要访问预测值，请在属性变量前加上美元符号 (`$`)。例如，您可以绑定到模型的 `isEnabled` 布尔值，这样[Toggle](../Toggle.zh-Hans.md) 就可以控制它的值：

```swift
struct MySubView: View {
    @ObservedObject var model: DataModel

    var body: some View {
        Toggle("Enabled", isOn: $model.isEnabled)
    }
}
```



## 获取值

- **wrappedValue**：观测对象引用的底层值。
- **ObservedObject.Wrapper**：底层可观察对象的包装器，可以创建与其属性的绑定。


---
source: https://developer.apple.com/documentation/SwiftUI/ObservedObject/projectedValue
crawled: 2025-12-02T21:00:24Z
---

# projectedValue

**Instance Property**

A projection of the observed object that creates bindings to its properties.

## Declaration

```swift
@MainActor @preconcurrency var projectedValue: ObservedObject<ObjectType>.Wrapper { get }
```

## Discussion

Use the projected value to get a [Binding](../Binding.zh-Hans.md) to a property of an observed object. To access the projected value, prefix the property variable with a dollar sign (`$`). For example, you can get a binding to a model’s `isEnabled` Boolean so that a [Toggle](../Toggle.zh-Hans.md) can control its value:

```swift
struct MySubView: View {
    @ObservedObject var model: DataModel

    var body: some View {
        Toggle("Enabled", isOn: $model.isEnabled)
    }
}
```



## Getting the value

- **wrappedValue**: The underlying value that the observed object references.
- **ObservedObject.Wrapper**: A wrapper of the underlying observable object that can create bindings to its properties.

