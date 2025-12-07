---
来源： https://developer.apple.com/documentation/SwiftUI/ForEachSectionCollection
抓取时间： 2025-12-02T17:40:09Z
---

# ForEachSectionCollection

**Structure**

该集合允许在 for each 循环中将视图视为其各部分的集合。

### 声明

```swift
struct ForEachSectionCollection<Content> where Content : View
```

## 概览

您不会直接使用此类型。SwiftUI 会代表您创建此类型。

## 迭代动态数据

- **ForEach**：一种结构，可根据需要从标识数据的底层集合中计算视图。
- **ForEachSubviewCollection**：一种集合，允许在 for each 循环中将视图视为其子视图的集合。
- **DynamicViewContent**：一种视图类型，可从底层数据集合生成视图。

## 符合

- 双向集合
- 集合
- 随机访问集合
- 序列


---
source: https://developer.apple.com/documentation/SwiftUI/ForEachSectionCollection
crawled: 2025-12-02T17:40:09Z
---

# ForEachSectionCollection

**Structure**

A collection which allows a view to be treated as a collection of its sections in a for each loop.

## Declaration

```swift
struct ForEachSectionCollection<Content> where Content : View
```

## Overview

You don’t use this type directly. Instead SwiftUI creates this type on your behalf.

## Iterating over dynamic data

- **ForEach**: A structure that computes views on demand from an underlying collection of identified data.
- **ForEachSubviewCollection**: A collection which allows a view to be treated as a collection of its subviews in a for each loop.
- **DynamicViewContent**: A type of view that generates views from an underlying collection of data.

## Conforms To

- BidirectionalCollection
- Collection
- RandomAccessCollection
- Sequence

