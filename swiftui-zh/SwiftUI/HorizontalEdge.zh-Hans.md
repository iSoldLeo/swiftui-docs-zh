--- 来源：https://developer.apple.com/documentation/SwiftUI/HorizontalEdge
抓取时间：2025-12-02T17:39:16Z

---

# HorizontalEdge

**Enumeration**

水平轴上的边。

## 声明

```swift
@frozen enum HorizontalEdge
```

## 概述

使用水平边可以执行诸如使用 [swipeActions(edge:allowsFullSwipe:content:)](View/swipeActions_edge_allowsFullSwipe_content.zh-Hans.md) 视图修饰符设置滑动操作之类的任务。前缘和后缘的位置取决于用户选择的区域设置。

## 获取边

- **HorizontalEdge.leading**：前缘。

- **HorizontalEdge.trailing**：后缘。

## 访问边集

- **HorizontalEdge.Set**：高效的水平边集。

## 访问边、区域和布局

- **Edge**：用于指示矩形一条边的枚举值。

- **Edge3D**：三维体的一个边或面。

- **VerticalEdge**：垂直轴上的边。

- **EdgeInsets**：矩形边的内嵌距离。

- **EdgeInsets3D**：三维体的各个面的内嵌距离。

## 符合以下规范

- 位可复制 (BitwiseCopyable)

- 可循环迭代 (CaseIterable)

- 可复制 (Copyable)

- 可解码 (Decodable)

- 可编码 (Encotable)

- 可等值 (Equatable)

- 可哈希 (Hashable)

- 原始表示 (RawRepresentable)

- 可发送 (Sendable)

- 可发送元类型 (SendableMetatype)


---
source: https://developer.apple.com/documentation/SwiftUI/HorizontalEdge
crawled: 2025-12-02T17:39:16Z
---

# HorizontalEdge

**Enumeration**

An edge on the horizontal axis.

## Declaration

```swift
@frozen enum HorizontalEdge
```

## Overview

Use a horizontal edge for tasks like setting a swipe action with the [swipeActions(edge:allowsFullSwipe:content:)](View/swipeActions_edge_allowsFullSwipe_content.zh-Hans.md) view modifier. The positions of the leading and trailing edges depend on the locale chosen by the user.

## Getting the edges

- **HorizontalEdge.leading**: The leading edge.
- **HorizontalEdge.trailing**: The trailing edge.

## Accessing sets of edges

- **HorizontalEdge.Set**: An efficient set of horizontal edges.

## Accessing edges, regions, and layouts

- **Edge**: An enumeration to indicate one edge of a rectangle.
- **Edge3D**: An edge or face of a 3D volume.
- **VerticalEdge**: An edge on the vertical axis.
- **EdgeInsets**: The inset distances for the sides of a rectangle.
- **EdgeInsets3D**: The inset distances for the faces of a 3D volume.

## Conforms To

- BitwiseCopyable
- CaseIterable
- Copyable
- Decodable
- Encodable
- Equatable
- Hashable
- RawRepresentable
- Sendable
- SendableMetatype

