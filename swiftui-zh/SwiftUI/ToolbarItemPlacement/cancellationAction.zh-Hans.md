---
来源： https://developer.apple.com/documentation/SwiftUI/ToolbarItemPlacement/cancellationAction
抓取时间： 2025-12-03T06:03:06Z
---

# 取消行动

**类型属性**

该项表示模式界面的取消操作。

## 声明

```swift
static let cancellationAction: ToolbarItemPlacement
```

## 讨论

取消操作通常是通过点击或单击 "取消 "按钮，在不采取任何操作的情况下取消模态界面。

在 macOS 和 Mac Catalyst 应用程序中，系统会将`cancellationAction` 项目放在工作表的后缘，但会放在任何[confirmationAction](confirmationAction.zh-Hans.md) 项目之前。

在 iOS、iPadOS、tvOS 和 watchOS 中，系统会将`cancellationAction` 项放在导航栏的前缘。

## 获取特定操作的位置

- **primaryAction**：该项目代表主要操作。
- **secondaryAction**：该项目代表次要操作。
- **confirmationAction**：该项目表示模式界面的确认操作。
- **destructiveAction**：该项目代表模式界面的确认操作：**destructiveAction**: 该项目表示模式界面的破坏性操作。
- **navigation**：该项目代表模式界面的破坏性操作：该项目表示导航操作。


---
source: https://developer.apple.com/documentation/SwiftUI/ToolbarItemPlacement/cancellationAction
crawled: 2025-12-03T06:03:06Z
---

# cancellationAction

**Type Property**

The item represents a cancellation action for a modal interface.

## Declaration

```swift
static let cancellationAction: ToolbarItemPlacement
```

## Discussion

Cancellation actions dismiss the modal interface without taking any action, usually by tapping or clicking a Cancel button.

In macOS and in Mac Catalyst apps, the system places `cancellationAction` items on the trailing edge of the sheet but places them before any [confirmationAction](confirmationAction.zh-Hans.md) items.

In iOS, iPadOS, tvOS, and watchOS, the system places `cancellationAction` items on the leading edge of the navigation bar.

## Getting placement for specific actions

- **primaryAction**: The item represents a primary action.
- **secondaryAction**: The item represents a secondary action.
- **confirmationAction**: The item represents a confirmation action for a modal interface.
- **destructiveAction**: The item represents a destructive action for a modal interface.
- **navigation**: The item represents a navigation action.

