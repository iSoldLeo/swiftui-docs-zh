--- 来源：https://developer.apple.com/documentation/swiftui/togglestyleconfiguration/ismixed

抓取时间：2025-12-04T13:11:37Z

---

# isMixed

**实例属性**

[Toggle](../Toggle.zh-Hans.md) 当前是否处于混合状态。

## 声明

```swift
var isMixed: Bool
```

## 说明

使用此属性确定切换样式是否应呈现混合状态。混合状态对应于包含真值和假值绑定的底层集合。要切换状态，请使用 [isOn](isOn.zh-Hans.md) 绑定上的 `Bool.toggle()` 方法。

在以下示例中，自定义样式使用 `isMixed` 属性，通过符号来渲染正确的切换状态：

```swift
struct SymbolToggleStyle: ToggleStyle {
    func makeBody(configuration: Configuration) -> some View {
        Button {
            configuration.isOn.toggle()
        } label: {
            Image(
                systemName: configuration.isMixed
                ? "minus.circle.fill" : configuration.isOn
                ? "checkmark.circle.fill" : "circle.fill")
            configuration.label
        }
    }
}
```

## 管理切换状态

- **isOn**：绑定到状态属性，该属性指示切换是否开启。

- **$isOn**


---
source: https://developer.apple.com/documentation/swiftui/togglestyleconfiguration/ismixed
crawled: 2025-12-04T13:11:37Z
---

# isMixed

**Instance Property**

Whether the [Toggle](../Toggle.zh-Hans.md) is currently in a mixed state.

## Declaration

```swift
var isMixed: Bool
```

## Discussion

Use this property to determine whether the toggle style should render a mixed state presentation. A mixed state corresponds to an underlying collection with a mix of true and false Bindings. To toggle the state, use the `Bool.toggle()` method on the [isOn](isOn.zh-Hans.md) binding.

In the following example, a custom style uses the `isMixed` property to render the correct toggle state using symbols:

```swift
struct SymbolToggleStyle: ToggleStyle {
    func makeBody(configuration: Configuration) -> some View {
        Button {
            configuration.isOn.toggle()
        } label: {
            Image(
                systemName: configuration.isMixed
                ? "minus.circle.fill" : configuration.isOn
                ? "checkmark.circle.fill" : "circle.fill")
            configuration.label
        }
    }
}
```

## Managing the toggle state

- **isOn**: A binding to a state property that indicates whether the toggle is on.
- **$isOn**

