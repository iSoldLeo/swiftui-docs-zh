--- 来源：https://developer.apple.com/documentation/swiftui/togglestyleconfiguration/ison
抓取时间：2025-12-04T13:11:38Z

---

# isOn

**实例属性**

绑定到状态属性，指示切换开关是否处于开启状态。

## 声明

```swift
@Binding var isOn: Bool { get nonmutating set }
```

## 说明

由于此值为 [Binding](../Binding.zh-Hans.md)，因此在定义自定义 [ToggleStyle](../ToggleStyle.zh-Hans.md) 时，您可以在 [makeBody(configuration:)](../ToggleStyle/makeBody_configuration.zh-Hans.md) 方法的实现中读取和写入此值。可通过该方法的 `configuration` 参数访问此值。

读取此值以设置切换开关的外观。例如，您可以根据 `isOn` 的值来选择空心圆或实心圆：

```swift
Image(systemName: configuration.isOn
    ? "checkmark.circle.fill"
    : "circle")
```

当用户执行旨在更改切换状态的操作时，写入此值。例如，您可以在 [Button](../Button.zh-Hans.md) 实例的 `action` 闭包内切换它：

```swift
Button {
    configuration.isOn.toggle()
} label: {
    // Draw the toggle.
}
```

## 管理切换状态

- **isMixed**：[Toggle](../Toggle.zh-Hans.md) 当前是否处于混合状态。

- **$isOn**


---
source: https://developer.apple.com/documentation/swiftui/togglestyleconfiguration/ison
crawled: 2025-12-04T13:11:38Z
---

# isOn

**Instance Property**

A binding to a state property that indicates whether the toggle is on.

## Declaration

```swift
@Binding var isOn: Bool { get nonmutating set }
```

## Discussion

Because this value is a [Binding](../Binding.zh-Hans.md), you can both read and write it in your implementation of the [makeBody(configuration:)](../ToggleStyle/makeBody_configuration.zh-Hans.md) method when defining a custom [ToggleStyle](../ToggleStyle.zh-Hans.md). Access it through that method’s `configuration` parameter.

Read this value to set the appearance of the toggle. For example, you can choose between empty and filled circles based on the `isOn` value:

```swift
Image(systemName: configuration.isOn
    ? "checkmark.circle.fill"
    : "circle")
```

Write this value when the user takes an action that’s meant to change the state of the toggle. For example, you can toggle it inside the `action` closure of a [Button](../Button.zh-Hans.md) instance:

```swift
Button {
    configuration.isOn.toggle()
} label: {
    // Draw the toggle.
}
```

## Managing the toggle state

- **isMixed**: Whether the [Toggle](../Toggle.zh-Hans.md) is currently in a mixed state.
- **$isOn**

