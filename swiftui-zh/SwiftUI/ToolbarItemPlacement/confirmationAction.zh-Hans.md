---
来源： https://developer.apple.com/documentation/SwiftUI/ToolbarItemPlacement/confirmationAction
抓取时间： 2025-12-03T06:03:05Z
---

# confirmationAction

**类型属性**

该项目代表模式界面的确认操作。

## 声明

```swift
static let confirmationAction: ToolbarItemPlacement
```

## 讨论

使用确认操作来接收用户对特定操作的确认。确认操作的一个例子是在日历中添加一个新事件的 "添加 "操作。

在 macOS 和 Mac Catalyst 应用程序中，系统会将`confirmationAction` 项目放在工作表最靠后位置的尾部边缘，并将应用程序的重点色作为背景色。

在 iOS、iPadOS 和 tvOS 中，系统会将`confirmationAction` 项放置在与[primaryAction](primaryAction.zh-Hans.md) 放置相同的位置。

在 watchOS 中，系统会将`confirmationAction` 项放在导航栏的尾部边缘。

## 获取特定操作的位置

- **primaryAction**：该项目代表主要操作。
- **secondaryAction**：该项目代表次要操作。
- **cancellationAction**：该项目表示模式界面的取消操作。
- **destructiveAction**：项目表示模式界面的取消操作：**destructiveAction**： 项目表示模式界面的破坏操作。
- **navigation**：该项目代表模式界面的破坏性操作：该项目表示导航操作。


---
source: https://developer.apple.com/documentation/SwiftUI/ToolbarItemPlacement/confirmationAction
crawled: 2025-12-03T06:03:05Z
---

# confirmationAction

**Type Property**

The item represents a confirmation action for a modal interface.

## Declaration

```swift
static let confirmationAction: ToolbarItemPlacement
```

## Discussion

Use confirmation actions to receive user confirmation of a particular action. An example of a confirmation action would be an action with the label “Add” to add a new event to the calendar.

In macOS and in Mac Catalyst apps, the system places `confirmationAction` items on the trailing edge in the trailing-most position of the sheet and gain the apps accent color as a background color.

In iOS, iPadOS, and tvOS, the system places `confirmationAction` items in the same location as a [primaryAction](primaryAction.zh-Hans.md) placement.

In watchOS, the system places `confirmationAction` items in the trailing edge of the navigation bar.

## Getting placement for specific actions

- **primaryAction**: The item represents a primary action.
- **secondaryAction**: The item represents a secondary action.
- **cancellationAction**: The item represents a cancellation action for a modal interface.
- **destructiveAction**: The item represents a destructive action for a modal interface.
- **navigation**: The item represents a navigation action.

