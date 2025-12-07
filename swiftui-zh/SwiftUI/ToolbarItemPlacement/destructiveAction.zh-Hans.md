---
来源： https://developer.apple.com/documentation/SwiftUI/ToolbarItemPlacement/destructiveAction
抓取时间： 2025-12-03T06:03:07Z
---

# 破坏性行动

**类型属性**

该项代表模式界面的破坏性动作。

## 声明

```swift
static let destructiveAction: ToolbarItemPlacement
```

## 讨论

破坏性操作表示与确认操作相反的操作。例如，标有 "不保存 "的按钮允许用户在退出前放弃对文档未保存的修改。

在 macOS 和 Mac Catalyst 应用程序中，系统会将`destructiveAction` 项目置于工作表的前缘，并赋予它们特殊的外观，以防意外使用。

在 iOS、tvOS 和 watchOS 中，系统会将`destructiveAction` 项目置于导航栏的尾部边缘。

## 获取特定操作的位置

- **primaryAction**：该项目代表主要操作。
- **secondaryAction**：该项目代表次要操作。
- **confirmationAction**：该项目表示模式界面的确认操作。
- **cancellationAction**： 该项目代表模式界面的确认操作：该项目表示模式界面的取消操作。
- **navigation**：项目表示模式界面的取消操作：该项目表示导航操作。


---
source: https://developer.apple.com/documentation/SwiftUI/ToolbarItemPlacement/destructiveAction
crawled: 2025-12-03T06:03:07Z
---

# destructiveAction

**Type Property**

The item represents a destructive action for a modal interface.

## Declaration

```swift
static let destructiveAction: ToolbarItemPlacement
```

## Discussion

Destructive actions represent the opposite of a confirmation action. For example, a button labeled “Don’t Save” that allows the user to discard unsaved changes to a document before quitting.

In macOS and in Mac Catalyst apps, the system places `destructiveAction` items in the leading edge of the sheet and gives them a special appearance to caution against accidental use.

In iOS, tvOS, and watchOS, the system places `destructiveAction` items in the trailing edge of the navigation bar.

## Getting placement for specific actions

- **primaryAction**: The item represents a primary action.
- **secondaryAction**: The item represents a secondary action.
- **confirmationAction**: The item represents a confirmation action for a modal interface.
- **cancellationAction**: The item represents a cancellation action for a modal interface.
- **navigation**: The item represents a navigation action.

