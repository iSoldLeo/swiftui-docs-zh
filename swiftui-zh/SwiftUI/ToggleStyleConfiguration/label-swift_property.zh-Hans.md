--- 来源：https://developer.apple.com/documentation/SwiftUI/ToggleStyleConfiguration/label-swift.property

抓取时间：2025-12-03T05:45:29Z

---

# 标签

**实例属性**

一个描述切换开关状态效果的视图。

## 声明

```swift
let label: ToggleStyleConfiguration.Label
```

## 说明

定义自定义 [ToggleStyle](../ToggleStyle.zh-Hans.md) 时，请在 [makeBody(configuration:)](../ToggleStyle/makeBody_configuration.zh-Hans.md) 方法的实现中使用此值。可通过该方法的 `configuration` 参数访问此值。

由于标签是 [View](../View.zh-Hans.md) 类型，因此您可以将其合并到样式定义返回的视图层次结构中。例如，您可以将标签与圆形图像组合在一起，如 [HStack](../HStack.zh-Hans.md)：

```swift
HStack {
    Image(systemName: configuration.isOn
        ? "checkmark.circle.fill"
        : "circle")
    configuration.label
}
```

## 获取标签视图

- **ToggleStyleConfiguration.Label**：切换按钮的已擦除文本标签。


---
source: https://developer.apple.com/documentation/SwiftUI/ToggleStyleConfiguration/label-swift.property
crawled: 2025-12-03T05:45:29Z
---

# label

**Instance Property**

A view that describes the effect of switching the toggle between states.

## Declaration

```swift
let label: ToggleStyleConfiguration.Label
```

## Discussion

Use this value in your implementation of the [makeBody(configuration:)](../ToggleStyle/makeBody_configuration.zh-Hans.md) method when defining a custom [ToggleStyle](../ToggleStyle.zh-Hans.md). Access it through the that method’s `configuration` parameter.

Because the label is a [View](../View.zh-Hans.md), you can incorporate it into the view hierarchy that you return from your style definition. For example, you can combine the label with a circle image in an [HStack](../HStack.zh-Hans.md):

```swift
HStack {
    Image(systemName: configuration.isOn
        ? "checkmark.circle.fill"
        : "circle")
    configuration.label
}
```

## Getting the label view

- **ToggleStyleConfiguration.Label**: A type-erased label of a toggle.

