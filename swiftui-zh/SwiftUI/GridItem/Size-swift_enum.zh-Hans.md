---
来源： https://developer.apple.com/documentation/SwiftUI/GridItem/Size-swift.enum
抓取时间： 2025-12-03T06:36:14Z
---

# GridItem.Size

**Enumeration**

网格布局中一行或多行或多列的小轴尺寸。

## 声明

```swift
enum Size
```

## 概览

创建[GridItem](../GridItem.zh-Hans.md) 时，使用`Size` 实例。该值告诉[LazyHGrid](../LazyHGrid.zh-Hans.md) 如何调整行的大小，或告诉[LazyVGrid](../LazyVGrid.zh-Hans.md) 如何调整列的大小。

## 获取大小

- **GridItem.Size.adaptive(minimum:maximum:)**：在单个灵活项目的空间内显示多个项目。
- **GridItem.Size.fixed(_:)**：具有指定固定尺寸的单个项目。
- **GridItem.Size.flexible(minimum:maximum:)**：单个灵活的项目。

## 检查网格项属性

- **alignment**：放置每个视图时使用的对齐方式。
- **spacing**：到下一个项目的间距。
- **size**：项目的大小，即列项目的宽度或行项目的高度。

## 符合

- 可复制
- 等价
- 可发送
- 可发送元数据类型


---
source: https://developer.apple.com/documentation/SwiftUI/GridItem/Size-swift.enum
crawled: 2025-12-03T06:36:14Z
---

# GridItem.Size

**Enumeration**

The size in the minor axis of one or more rows or columns in a grid layout.

## Declaration

```swift
enum Size
```

## Overview

Use a `Size` instance when you create a [GridItem](../GridItem.zh-Hans.md). The value tells a [LazyHGrid](../LazyHGrid.zh-Hans.md) how to size its rows, or a [LazyVGrid](../LazyVGrid.zh-Hans.md) how to size its columns.

## Getting the sizes

- **GridItem.Size.adaptive(minimum:maximum:)**: Multiple items in the space of a single flexible item.
- **GridItem.Size.fixed(_:)**: A single item with the specified fixed size.
- **GridItem.Size.flexible(minimum:maximum:)**: A single flexible item.

## Inspecting grid item properties

- **alignment**: The alignment to use when placing each view.
- **spacing**: The spacing to the next item.
- **size**: The size of the item, which is the width of a column item or the height of a row item.

## Conforms To

- Copyable
- Equatable
- Sendable
- SendableMetatype

