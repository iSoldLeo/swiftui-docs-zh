--- 来源：https://developer.apple.com/documentation/SwiftUI/View/labelsHidden()

抓取时间：2025-11-30T21:17:41Z

---

# labelsHidden()

**实例方法**

隐藏此视图中所有控件的标签。

## 声明

```swift
nonisolated func labelsHidden() -> some View

```

## 说明

当您想要从用户界面中的一个或多个控件中省略标签时，请使用此修饰符。例如，以下示例中的第一个 [Toggle](../Toggle.zh-Hans.md) 会隐藏其标签：

```swift
VStack {
    Toggle(isOn: $toggle1) {
        Text("Toggle 1")
    }
    .labelsHidden()

    Toggle(isOn: $toggle2) {
        Text("Toggle 2")
    }
}
```

上述示例中的 [VStack](../VStack.zh-Hans.md) 会将第一个切换按钮的控件元素居中显示在可用空间中，同时将第二个切换按钮的标签和控件元素组合在一起居中显示：

即使隐藏标签，也务必为控件提供标签，因为 SwiftUI 会将标签用于其他用途，包括辅助功能。

## 隐藏系统元素

- **labelsVisibility(_:)**：控制此视图中包含的任何控件的标签的可见性。

- **labelsVisibility**：[labelsVisibility(_:)](labelsVisibility.zh-Hans.md) 设置的标签可见性。

- **menuIndicator(_:)**：设置此视图中控件的菜单指示器的可见性。

- **statusBarHidden(_:)**：设置状态栏的可见性。

- **persistentSystemOverlays(_:)**：设置覆盖在应用上的非瞬态系统视图的首选可见性。

- **Visibility**：根据平台、当前上下文和其他因素自动选择 UI 元素的可见性。


---
source: https://developer.apple.com/documentation/SwiftUI/View/labelsHidden()
crawled: 2025-11-30T21:17:41Z
---

# labelsHidden()

**Instance Method**

Hides the labels of any controls contained within this view.

## Declaration

```swift
nonisolated func labelsHidden() -> some View

```

## Discussion

Use this modifier when you want to omit a label from one or more controls in your user interface. For example, the first [Toggle](../Toggle.zh-Hans.md) in the following example hides its label:

```swift
VStack {
    Toggle(isOn: $toggle1) {
        Text("Toggle 1")
    }
    .labelsHidden()

    Toggle(isOn: $toggle2) {
        Text("Toggle 2")
    }
}
```

The [VStack](../VStack.zh-Hans.md) in the example above centers the first toggle’s control element in the available space, while it centers the second toggle’s combined label and control element:



Always provide a label for controls, even when you hide the label, because SwiftUI uses labels for other purposes, including accessibility.



## Hiding system elements

- **labelsVisibility(_:)**: Controls the visibility of labels of any controls contained within this view.
- **labelsVisibility**: The labels visibility set by [labelsVisibility(_:)](labelsVisibility.zh-Hans.md).
- **menuIndicator(_:)**: Sets the menu indicator visibility for controls within this view.
- **statusBarHidden(_:)**: Sets the visibility of the status bar.
- **persistentSystemOverlays(_:)**: Sets the preferred visibility of the non-transient system views overlaying the app.
- **Visibility**: The visibility of a UI element, chosen automatically based on the platform, current context, and other factors.

