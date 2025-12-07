---
来源： https://developer.apple.com/documentation/SwiftUI/NavigationSplitViewVisibility
抓取时间： 2025-12-02T16:15:51Z
---

# 导航分割视图可见性

**Structure**

导航分割视图中前导列的可见性。

## 声明

```swift
struct NavigationSplitViewVisibility
```

## 概览

使用该类型的值可控制[NavigationSplitView](NavigationSplitView.zh-Hans.md) 中各列的可见性。创建具有该类型值的[State](State.zh-Hans.md) 属性，并在创建导航分割视图时将[Binding](Binding.zh-Hans.md) 传递给[init(columnVisibility:sidebar:detail:)](NavigationSplitView/init_columnVisibility_sidebar_detail.zh-Hans.md) 或[init(columnVisibility:sidebar:content:detail:)](NavigationSplitView/init_columnVisibility_sidebar_content_detail.zh-Hans.md) 初始化器。然后，您可以在代码的其他地方修改该值：

- 使用 [detailOnly](NavigationSplitViewVisibility/detailOnly.zh-Hans.md) 隐藏除尾部列以外的所有列。
- 使用 [doubleColumn](NavigationSplitViewVisibility/doubleColumn.zh-Hans.md) 隐藏三栏导航拆分视图的前导栏。
- 使用 [all](NavigationSplitViewVisibility/all.zh-Hans.md) 显示所有列。
- 使用 [automatic](NavigationSplitViewVisibility/automatic.zh-Hans.md)，依赖当前上下文的自动行为。



## 获取可见性

- **automatic**：使用当前设备的默认前导列可见性。
- **all**：显示三列导航分割视图的所有列。
- **doubleColumn**：显示三栏导航拆分视图的内容栏和详细区域，或显示两栏导航拆分视图的侧边栏和详细区域。
- **detailOnly**：隐藏三栏导航拆分视图的前两栏，以便只显示详细区域。

## 以列的形式显示视图

- 为 SwiftUI 应用程序带来强大的导航结构**：使用导航链接、堆栈、目的地和路径为所有平台提供简化的体验，以及深度链接和状态恢复等行为。
- 迁移到新的导航类型**：将导航视图替换为导航堆栈和导航分割视图，从而改进应用程序中的导航行为。
- **NavigationSplitView**：一种以两列或三列显示视图的视图，在前导列中的选择可控制后续列的显示。
- **navigationSplitViewStyle(_:)**：设置该视图中导航分割视图的样式。
- **navigationSplitViewColumnWidth(_:)**：为包含此视图的列设置固定的首选宽度。
- **navigationSplitViewColumnWidth(min:ideal:max:)**：为包含此视图的列设置灵活的首选宽度。
- **NavigationLink**：控制导航演示的视图。

## 符合

- 可解码
- 可编码
- 可等价
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/NavigationSplitViewVisibility
crawled: 2025-12-02T16:15:51Z
---

# NavigationSplitViewVisibility

**Structure**

The visibility of the leading columns in a navigation split view.

## Declaration

```swift
struct NavigationSplitViewVisibility
```

## Overview

Use a value of this type to control the visibility of the columns of a [NavigationSplitView](NavigationSplitView.zh-Hans.md). Create a [State](State.zh-Hans.md) property with a value of this type, and pass a [Binding](Binding.zh-Hans.md) to that state to the [init(columnVisibility:sidebar:detail:)](NavigationSplitView/init_columnVisibility_sidebar_detail.zh-Hans.md) or [init(columnVisibility:sidebar:content:detail:)](NavigationSplitView/init_columnVisibility_sidebar_content_detail.zh-Hans.md) initializer when you create the navigation split view. You can then modify the value elsewhere in your code to:

- Hide all but the trailing column with [detailOnly](NavigationSplitViewVisibility/detailOnly.zh-Hans.md).
- Hide the leading column of a three-column navigation split view with [doubleColumn](NavigationSplitViewVisibility/doubleColumn.zh-Hans.md).
- Show all the columns with [all](NavigationSplitViewVisibility/all.zh-Hans.md).
- Rely on the automatic behavior for the current context with [automatic](NavigationSplitViewVisibility/automatic.zh-Hans.md).



## Getting visibilities

- **automatic**: Use the default leading column visibility for the current device.
- **all**: Show all the columns of a three-column navigation split view.
- **doubleColumn**: Show the content column and detail area of a three-column navigation split view, or the sidebar column and detail area of a two-column navigation split view.
- **detailOnly**: Hide the leading two columns of a three-column navigation split view, so that just the detail area shows.

## Presenting views in columns

- **Bringing robust navigation structure to your SwiftUI app**: Use navigation links, stacks, destinations, and paths to provide a streamlined experience for all platforms, as well as behaviors such as deep linking and state restoration.
- **Migrating to new navigation types**: Improve navigation behavior in your app by replacing navigation views with navigation stacks and navigation split views.
- **NavigationSplitView**: A view that presents views in two or three columns, where selections in leading columns control presentations in subsequent columns.
- **navigationSplitViewStyle(_:)**: Sets the style for navigation split views within this view.
- **navigationSplitViewColumnWidth(_:)**: Sets a fixed, preferred width for the column containing this view.
- **navigationSplitViewColumnWidth(min:ideal:max:)**: Sets a flexible, preferred width for the column containing this view.
- **NavigationLink**: A view that controls a navigation presentation.

## Conforms To

- Decodable
- Encodable
- Equatable
- Sendable
- SendableMetatype

