---
来源： https://developer.apple.com/documentation/SwiftUI/ToolbarItemPlacement/navigation
抓取时间： 2025-12-03T06:03:08Z
---

# 导航

**类型属性**

项目代表导航操作。

## 声明

```swift
static let navigation: ToolbarItemPlacement
```

## 讨论

导航操作允许用户在上下文之间移动。例如，网页浏览器的前进和后退按钮就是导航操作。

在 macOS 和 Mac Catalyst 应用程序中，如果工具栏中存在内嵌标题，系统会将导航项放在工具栏前缘，而不是内嵌标题。

在 iOS、iPadOS 和 tvOS 中，导航项目会出现在导航栏的前缘。如果系统导航项（如返回按钮）出现在紧凑宽度中，则会显示在[primaryAction](primaryAction.zh-Hans.md)位置。

## 获取特定操作的位置

- **primaryAction**：项目代表主要操作。
- **secondaryAction**：该项目代表次要操作。
- **confirmationAction**：该项目表示模式界面的确认操作。
- **cancellationAction**：该项目代表模式界面的确认操作：该项目表示模式界面的取消操作。
- **destructiveAction**：项目表示模式界面的取消操作：该项目表示模式界面的取消操作。


---
source: https://developer.apple.com/documentation/SwiftUI/ToolbarItemPlacement/navigation
crawled: 2025-12-03T06:03:08Z
---

# navigation

**Type Property**

The item represents a navigation action.

## Declaration

```swift
static let navigation: ToolbarItemPlacement
```

## Discussion

Navigation actions allow the user to move between contexts. For example, the forward and back buttons of a web browser are navigation actions.

In macOS and in Mac Catalyst apps, the system places navigation items in the leading edge of the toolbar ahead of the inline title if that is present in the toolbar.

In iOS, iPadOS, and tvOS, navigation items appear in the leading edge of the navigation bar. If a system navigation item such as a back button is present in a compact width, it instead appears in the [primaryAction](primaryAction.zh-Hans.md) placement.

## Getting placement for specific actions

- **primaryAction**: The item represents a primary action.
- **secondaryAction**: The item represents a secondary action.
- **confirmationAction**: The item represents a confirmation action for a modal interface.
- **cancellationAction**: The item represents a cancellation action for a modal interface.
- **destructiveAction**: The item represents a destructive action for a modal interface.

