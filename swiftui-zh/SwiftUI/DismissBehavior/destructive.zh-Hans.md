---
来源： https://developer.apple.com/documentation/SwiftUI/DismissBehavior/destructive
抓取时间： 2025-12-03T05:32:02Z
---

# 破坏性

**类型属性**

破坏性解散行为。

## 声明

```swift
static let destructive: DismissBehavior
```

## 讨论

当您想解除窗口时，请使用此行为，而不必考虑通常会阻止解除窗口的任何条件。在这种情况下解散窗口可能会导致状态丢失。

在 macOS 上，即使窗口当前显示的是模式演示（如工作表或警报），此行为也会导致窗口解散。此外，当有未保存的更改时，文档窗口将不会显示保存对话框，而该窗口是通过此行为解散的。

在 iOS 上，该行为与 `interactive`的行为相同。

## 获取行为

- **interactive**：交互式解散行为。


---
source: https://developer.apple.com/documentation/SwiftUI/DismissBehavior/destructive
crawled: 2025-12-03T05:32:02Z
---

# destructive

**Type Property**

The destructive dismiss behavior.

## Declaration

```swift
static let destructive: DismissBehavior
```

## Discussion

Use this behavior when you want to dismiss a window regardless of any conditions that would normally prevent the dismissal. Dismissing windows in this matter may result in loss of state.

On macOS, this behavior will cause windows to dismiss even when they are currently showing a modal presentation, such as a sheet or alert. Additionally, a document window will not show the save dialog when there are unsaved changes and the window is dismissed with this behavior.

On iOS, this behavior behaves the same as `interactive`.

## Getting behaviors

- **interactive**: The interactive dismiss behavior.

