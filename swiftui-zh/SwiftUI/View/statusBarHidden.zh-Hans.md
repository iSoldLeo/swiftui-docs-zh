--- 来源：https://developer.apple.com/documentation/SwiftUI/View/statusBarHidden(_:)

抓取时间：2025-12-02T17:32:38Z

---

# statusBarHidden(_:)

**实例方法**

设置状态栏的可见性。

## 声明

```swift
nonisolated func statusBarHidden(_ hidden: Bool = true) -> some View

```

## 参数

- **hidden**：一个布尔值，指示是否隐藏状态栏。

## 隐藏系统元素

- **labelsHidden()**：隐藏此视图中包含的任何控件的标签。

- **labelsVisibility(_:)**：控制此视图中包含的任何控件的标签的可见性。

- **labelsVisibility**：由 [labelsVisibility(_:)](labelsVisibility.zh-Hans.md) 设置的标签可见性。

- **menuIndicator(_:)**：设置此视图中控件的菜单指示器可见性。

- **persistentSystemOverlays(_:)**：设置覆盖在应用程序上的非瞬态系统视图的首选可见性。

- **Visibility**：UI 元素的可见性，根据平台、当前上下文和其他因素自动选择。


---
source: https://developer.apple.com/documentation/SwiftUI/View/statusBarHidden(_:)
crawled: 2025-12-02T17:32:38Z
---

# statusBarHidden(_:)

**Instance Method**

Sets the visibility of the status bar.

## Declaration

```swift
nonisolated func statusBarHidden(_ hidden: Bool = true) -> some View

```

## Parameters

- **hidden**: A Boolean value that indicates whether to hide the status bar.

## Hiding system elements

- **labelsHidden()**: Hides the labels of any controls contained within this view.
- **labelsVisibility(_:)**: Controls the visibility of labels of any controls contained within this view.
- **labelsVisibility**: The labels visibility set by [labelsVisibility(_:)](labelsVisibility.zh-Hans.md).
- **menuIndicator(_:)**: Sets the menu indicator visibility for controls within this view.
- **persistentSystemOverlays(_:)**: Sets the preferred visibility of the non-transient system views overlaying the app.
- **Visibility**: The visibility of a UI element, chosen automatically based on the platform, current context, and other factors.

