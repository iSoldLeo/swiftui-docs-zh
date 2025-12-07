---
来源： https://developer.apple.com/documentation/SwiftUI/DismissBehavior/interactive
抓取时间： 2025-12-03T05:32:03Z
---

# 交互式

**类型属性**

交互式解除行为。

## 声明

```swift
static let interactive: DismissBehavior
```

## 讨论

当您想以类似于标准系统功能的方式（例如，当用户单击关闭按钮时）关闭窗口时，请使用此行为。

这是 macOS 和 iOS 上的默认行为。

在 macOS 上，使用此行为取消窗口不会取消当前正在显示模式演示（如工作表或警报）的窗口。此外，如果文档有未保存的更改，则使用此行为解散的文档窗口将显示保存对话框。

在 iOS 上，无论是否显示任何模式演示，使用此行为解散窗口都将解散该窗口。

## 获取行为

- **destructive**：破坏性解散行为。


---
source: https://developer.apple.com/documentation/SwiftUI/DismissBehavior/interactive
crawled: 2025-12-03T05:32:03Z
---

# interactive

**Type Property**

The interactive dismiss behavior.

## Declaration

```swift
static let interactive: DismissBehavior
```

## Discussion

Use this behavior when you want to dismiss a window in a manner that is similar to the standard system affordances for window dismissal - for example, when a user clicks the close button.

This is the default behavior on macOS and iOS.

On macOS, dismissing a window using this behavior will not dismiss a window which is currently showing a modal presentation, such as a sheet or alert. Additionally, a document window that is dismissed with this behavior will show the save dialog if there are unsaved changes to the document.

On iOS, dismissing a window using this behavior will dismiss it regardless of any modal presentations being shown.

## Getting behaviors

- **destructive**: The destructive dismiss behavior.

