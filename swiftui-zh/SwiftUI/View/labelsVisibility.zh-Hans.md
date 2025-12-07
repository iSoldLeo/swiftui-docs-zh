--- 来源：https://developer.apple.com/documentation/SwiftUI/View/labelsVisibility(_:)

抓取时间：2025-12-02T17:24:09Z

---

# labelsVisibility(_:)

**实例方法**

控制此视图中包含的任何控件的标签的可见性。

## 声明

```swift
nonisolated func labelsVisibility(_ visibility: Visibility) -> some View

```

## 说明

当您想要从用户界面中的一个或多个带标签的内容中省略某个标签时，请使用此修饰符。例如，以下示例中的第一个 [Toggle](../Toggle.zh-Hans.md) 会隐藏其标签：

```swift
VStack {
    Toggle(isOn: $toggle1) {
        Text("Toggle 1")
    }
    .labelsVisibility(.hidden)

    Toggle(isOn: $toggle2) {
        Text("Toggle 2")
    }
}
```

上述示例中的 [VStack](../VStack.zh-Hans.md) 会将第一个切换按钮的控件元素居中显示在可用空间中，同时将第二个切换按钮的标签和控件元素组合在一起居中显示：

即使隐藏标签，也务必为控件提供标签，因为 SwiftUI 会将标签用于其他用途，包括辅助功能。

在 iOS 上，`Menu` 内的 `Picker` 默认会隐藏其标签。您可以使用此修饰符显式显示该上下文中的标签：

```swift
Menu {
    Picker("Flavor", selection: $selectedFlavor) {
        Text("Chocolate").tag(Flavor.chocolate)
        Text("Vanilla").tag(Flavor.vanilla)
        Text("Strawberry").tag(Flavor.strawberry)
    }
    .labelsVisibility(.visible)
}
```

## 隐藏系统元素

- **labelsHidden()**：隐藏此视图中包含的所有控件的标签。

- **labelsVisibility**：由 [labelsVisibility(_:)](labelsVisibility.zh-Hans.md) 设置的标签可见性。

- **menuIndicator(_:)**：设置此视图中控件的菜单指示器可见性。

- **statusBarHidden(_:)**：设置状态栏的可见性。

- **persistentSystemOverlays(_:)**：设置覆盖在应用程序上的非瞬态系统视图的首选可见性。

- **Visibility**：UI 元素的可见性，根据平台、当前上下文和其他因素自动选择。


---
source: https://developer.apple.com/documentation/SwiftUI/View/labelsVisibility(_:)
crawled: 2025-12-02T17:24:09Z
---

# labelsVisibility(_:)

**Instance Method**

Controls the visibility of labels of any controls contained within this view.

## Declaration

```swift
nonisolated func labelsVisibility(_ visibility: Visibility) -> some View

```

## Discussion

Use this modifier when you want to omit a label from one or more labeled content in your user interface. For example, the first [Toggle](../Toggle.zh-Hans.md) in the following example hides its label:

```swift
VStack {
    Toggle(isOn: $toggle1) {
        Text("Toggle 1")
    }
    .labelsVisibility(.hidden)

    Toggle(isOn: $toggle2) {
        Text("Toggle 2")
    }
}
```

The [VStack](../VStack.zh-Hans.md) in the example above centers the first toggle’s control element in the available space, while it centers the second toggle’s combined label and control element:



Always provide a label for controls, even when you hide the label, because SwiftUI uses labels for other purposes, including accessibility.

On iOS, a `Picker` within a `Menu` hides its label by default. You can use this modifier to explicitly show the label in that context:

```swift
Menu {
    Picker("Flavor", selection: $selectedFlavor) {
        Text("Chocolate").tag(Flavor.chocolate)
        Text("Vanilla").tag(Flavor.vanilla)
        Text("Strawberry").tag(Flavor.strawberry)
    }
    .labelsVisibility(.visible)
}
```



## Hiding system elements

- **labelsHidden()**: Hides the labels of any controls contained within this view.
- **labelsVisibility**: The labels visibility set by [labelsVisibility(_:)](labelsVisibility.zh-Hans.md).
- **menuIndicator(_:)**: Sets the menu indicator visibility for controls within this view.
- **statusBarHidden(_:)**: Sets the visibility of the status bar.
- **persistentSystemOverlays(_:)**: Sets the preferred visibility of the non-transient system views overlaying the app.
- **Visibility**: The visibility of a UI element, chosen automatically based on the platform, current context, and other factors.

