---
来源： https://developer.apple.com/documentation/SwiftUI/ToolbarItemPlacement/status
抓取时间： 2025-12-03T06:03:02Z
---

# 状态

**类型属性**

项目表示当前上下文的状态变化。

## 声明

```swift
static let status: ToolbarItemPlacement
```

## 讨论

状态项属于信息性质，不代表用户可以采取的行动。例如，一条显示最后一次与服务器通信的时间的信息，以检查是否有新邮件。

在 macOS 和 Mac Catalyst 应用程序中，系统会将状态项放在工具栏的中央。

在 iOS 和 iPadOS 中，系统会将状态项目放在底部工具栏的中央。

在 tvOS 中，只有在[NavigationSplitView](../NavigationSplitView.zh-Hans.md) 的侧边栏中才有这种位置。  系统会将状态项目放置在导航侧边栏底部工具栏的中央。  如果在其他地方使用，则没有任何效果。

## 获取语义位置

- **automatic**：系统会根据平台、尺寸等级或是否存在其他物品等多种因素自动放置物品。
- **principal**：系统将物品放置在主要物品区。


---
source: https://developer.apple.com/documentation/SwiftUI/ToolbarItemPlacement/status
crawled: 2025-12-03T06:03:02Z
---

# status

**Type Property**

The item represents a change in status for the current context.

## Declaration

```swift
static let status: ToolbarItemPlacement
```

## Discussion

Status items are informational in nature, and don’t represent an action that can be taken by the user. For example, a message that indicates the time of the last communication with the server to check for new messages.

In macOS and in Mac Catalyst apps, the system places status items in the center of the toolbar.

In iOS and iPadOS, the system places status items in the center of the bottom toolbar.

In tvOS, this placement is only available from within the sidebar of a [NavigationSplitView](../NavigationSplitView.zh-Hans.md).  The system places status items in the center of the bottom toolbar within the navigation sidebar.  It has no effect if used elsewhere.

## Getting semantic placement

- **automatic**: The system places the item automatically, depending on many factors including the platform, size class, or presence of other items.
- **principal**: The system places the item in the principal item section.

