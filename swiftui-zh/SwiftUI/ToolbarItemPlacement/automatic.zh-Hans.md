---
来源： https://developer.apple.com/documentation/SwiftUI/ToolbarItemPlacement/automatic
抓取时间： 2025-12-03T06:03:01Z
---

# 自动

**类型属性**

系统会根据平台、尺寸等级或是否存在其他物品等多种因素自动放置物品。

### 声明

```swift
static let automatic: ToolbarItemPlacement
```

## 讨论

在 macOS 和 Mac Catalyst 应用程序中，系统会按从上到下的顺序排列当前工具栏中的项目。在 watchOS 上，只有第一个项目会出现，并固定在导航栏下方。

在 iPadOS 中，如果导航栏支持自定义，系统会将项目置于导航栏中央。否则，系统会将项目置于导航栏的尾部位置。

在 iOS 和 tvOS 中，系统会将项目放在导航栏的尾部位置。

在 iOS、iPadOS 和 macOS 中，系统会使用工具栏的可用空间来决定在工具栏中呈现多少个项目。如果可用空间无法容纳所有项目，系统可能会创建一个溢出菜单，并将剩余项目放置在该菜单中。

### 获取语义位置

- **principal**：系统将项目置于主项目部分。
- **status**：该项目表示当前上下文的状态发生变化。


---
source: https://developer.apple.com/documentation/SwiftUI/ToolbarItemPlacement/automatic
crawled: 2025-12-03T06:03:01Z
---

# automatic

**Type Property**

The system places the item automatically, depending on many factors including the platform, size class, or presence of other items.

## Declaration

```swift
static let automatic: ToolbarItemPlacement
```

## Discussion

In macOS and in Mac Catalyst apps, the system places items in the current toolbar section in order of leading to trailing. On watchOS, only the first item appears, pinned beneath the navigation bar.

In iPadOS, the system places items in the center of the navigation bar if the navigation bar supports customization. Otherwise, it places items in the trailing position of the navigation bar.

In iOS, and tvOS, the system places items in the trailing position of the navigation bar.

In iOS, iPadOS, and macOS, the system uses the space available to the toolbar when determining how many items to render in the toolbar. If not all items fit in the available space, an overflow menu may be created and remaining items placed in that menu.

## Getting semantic placement

- **principal**: The system places the item in the principal item section.
- **status**: The item represents a change in status for the current context.

