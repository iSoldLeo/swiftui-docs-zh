---
来源： https://developer.apple.com/documentation/SwiftUI/ViewSpacing
抓取时间： 2025-12-02T17:39:22Z
---

# ViewSpacing

**Structure**

视图的几何间距偏好集合。

## 声明

```swift
struct ViewSpacing
```

## 概览

该类型表示布局中一个视图与下一个视图之间的空间大小。该类型存储了顶边、底边、前缘和后缘的独立值，还可以为不同类型的相邻视图记录不同的值。例如，该类型可能包含一个沿顶部和底部边缘到下一个文本视图的间距值，其他边缘到文本视图的间距值，以及其他类型视图的其他值。间距偏好也会因平台而异。

您的[Layout](Layout.zh-Hans.md) 类型不必考虑首选间距，但如果需要，您可以使用布局容器中子视图的[spacing](LayoutSubview/spacing.zh-Hans.md) 首选项：

- 在执行[placeSubviews(in:proposal:subviews:cache:)](Layout/placeSubviews_in_proposal_subviews_cache.zh-Hans.md) 方法时，在子视图之间添加间距。
- 通过执行 [spacing(subviews:cache:)](Layout/spacing_subviews_cache.zh-Hans.md) 方法为容器视图创建间距首选项实例。

## 创建间距实例

- **init()**：使用默认间距值初始化一个实例。
- **zero**：视图间距实例，所有边上的值都为零。

## 测量间距

- **distance(to:along:)**：沿指定轴向获取返回指定间距偏好的视图的首选间距。

## 合并间距实例

- **formUnion(_:edges:)**：针对指定的边集，将另一个间距实例的间距首选项与此实例的间距首选项合并。
- **union(_:edges:)**：获取一个新值，用于将另一个间距实例的间距首选项与此实例的间距首选项合并为一组指定的边。

## 配置自定义布局

- **LayoutProperties**：布局容器的特定布局属性。
- **ProposedViewSize**：关于视图大小的建议。

## 符合

- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/ViewSpacing
crawled: 2025-12-02T17:39:22Z
---

# ViewSpacing

**Structure**

A collection of the geometric spacing preferences of a view.

## Declaration

```swift
struct ViewSpacing
```

## Overview

This type represents how much space a view prefers to have between it and the next view in a layout. The type stores independent values for each of the top, bottom, leading, and trailing edges, and can also record different values for different kinds of adjacent views. For example, it might contain one value for the spacing to the next text view along the top and bottom edges, other values for the spacing to text views on other edges, and yet other values for other kinds of views. Spacing preferences can also vary by platform.

Your [Layout](Layout.zh-Hans.md) type doesn’t have to take preferred spacing into account, but if it does, you can use the [spacing](LayoutSubview/spacing.zh-Hans.md) preferences of the subviews in your layout container to:

- Add space between subviews when you implement the [placeSubviews(in:proposal:subviews:cache:)](Layout/placeSubviews_in_proposal_subviews_cache.zh-Hans.md) method.
- Create a spacing preferences instance for the container view by implementing the [spacing(subviews:cache:)](Layout/spacing_subviews_cache.zh-Hans.md) method.

## Creating spacing instances

- **init()**: Initializes an instance with default spacing values.
- **zero**: A view spacing instance that contains zero on all edges.

## Measuring spacing distance

- **distance(to:along:)**: Gets the preferred spacing distance along the specified axis to the view that returns a specified spacing preference.

## Merging spacing instances

- **formUnion(_:edges:)**: Merges the spacing preferences of another spacing instance with this instance for a specified set of edges.
- **union(_:edges:)**: Gets a new value that merges the spacing preferences of another spacing instance with this instance for a specified set of edges.

## Configuring a custom layout

- **LayoutProperties**: Layout-specific properties of a layout container.
- **ProposedViewSize**: A proposal for the size of a view.

## Conforms To

- Sendable
- SendableMetatype

