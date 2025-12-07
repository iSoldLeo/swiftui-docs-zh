---
来源： https://developer.apple.com/documentation/SwiftUI/ToolbarItemPlacement/principal
抓取时间： 2025-12-03T06:03:01Z
---

# 校长

**类型属性**

系统将项目置于主要项目部分。

## 声明

```swift
static let principal: ToolbarItemPlacement
```

## 讨论

主要操作是功能的关键单元，放在显著位置。例如，网页浏览器的位置字段就是一个主要项目。

在 macOS 和 Mac Catalyst 应用程序中，系统会将主要项目放在工具栏的中央。

在 iOS、iPadOS 和 tvOS 中，系统会将主项放在导航栏的中央。该项目优先于通过 `View/navigationTitle` 指定的标题。

## 获取语义位置

- **automatic**：系统会根据平台、尺寸等级或是否存在其他物品等多种因素自动放置物品。
- **status**：该项目代表当前上下文中状态的改变。


---
source: https://developer.apple.com/documentation/SwiftUI/ToolbarItemPlacement/principal
crawled: 2025-12-03T06:03:01Z
---

# principal

**Type Property**

The system places the item in the principal item section.

## Declaration

```swift
static let principal: ToolbarItemPlacement
```

## Discussion

Principal actions are key units of functionality that receive prominent placement. For example, the location field for a web browser is a principal item.

In macOS and in Mac Catalyst apps, the system places the principal item in the center of the toolbar.

In iOS, iPadOS, and tvOS, the system places the principal item in the center of the navigation bar. This item takes precedent over a title specified through `View/navigationTitle`.

## Getting semantic placement

- **automatic**: The system places the item automatically, depending on many factors including the platform, size class, or presence of other items.
- **status**: The item represents a change in status for the current context.

