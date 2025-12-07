---
来源： https://developer.apple.com/documentation/SwiftUI/ToolbarItemPlacement/primaryAction
抓取时间： 2025-12-03T06:03:03Z
---

# primaryAction

**类型属性**

该项目代表主要操作。

## 声明

```swift
static let primaryAction: ToolbarItemPlacement
```

## 讨论

主要操作是当前上下文中较常用的操作。例如，用户在聊天应用程序中点击或轻按按钮来撰写新信息。

在 macOS 和 Mac Catalyst 应用程序中，主要操作的位置是工具栏的前缘。

在 iOS、iPadOS 和 tvOS 中，主要操作的位置是导航栏的后缘。

在 watchOS 中，系统将主要操作放在导航栏下方；用户通过滚动来显示操作。

## 获取特定操作的位置

- **secondaryAction**：该项目代表二级操作。
- **confirmationAction**：该项目表示模式界面的确认操作。
- **cancellationAction**：该项目代表模式界面的确认操作：该项目表示模式界面的取消操作。
- **destructiveAction**：项目表示模式界面的取消操作：**destructiveAction**： 项目表示模式界面的破坏操作。
- **navigation**：项目表示模式界面的破坏性操作：该项目表示导航操作。


---
source: https://developer.apple.com/documentation/SwiftUI/ToolbarItemPlacement/primaryAction
crawled: 2025-12-03T06:03:03Z
---

# primaryAction

**Type Property**

The item represents a primary action.

## Declaration

```swift
static let primaryAction: ToolbarItemPlacement
```

## Discussion

A primary action is a more frequently used action for the current context. For example, a button the user clicks or taps to compose a new message in a chat app.

In macOS and in Mac Catalyst apps, the location for the primary action is the leading edge of the toolbar.

In iOS, iPadOS, and tvOS, the location for the primary action is the trailing edge of the navigation bar.

In watchOS the system places the primary action beneath the navigation bar; the user reveals the action by scrolling.

## Getting placement for specific actions

- **secondaryAction**: The item represents a secondary action.
- **confirmationAction**: The item represents a confirmation action for a modal interface.
- **cancellationAction**: The item represents a cancellation action for a modal interface.
- **destructiveAction**: The item represents a destructive action for a modal interface.
- **navigation**: The item represents a navigation action.

