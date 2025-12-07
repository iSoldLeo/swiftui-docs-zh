--- 来源：https://developer.apple.com/documentation/SwiftUI/ForEachSubviewCollection

抓取时间：2025-12-02T17:40:10Z

---

# ForEachSubviewCollection

**Structure**

一个集合，允许在 for each 循环中将视图视为其子视图的集合。

## 声明

```swift
struct ForEachSubviewCollection<Content> where Content : View
```

## 迭代动态数据

- **ForEach**：一个结构，可以根据底层已识别数据集合按需计算视图。

- **ForEachSectionCollection**：一个集合，允许在 for each 循环中将视图视为其部分集合。

- **DynamicViewContent**：一种视图类型，可以根据底层数据集合生成视图。

## 符合以下标准

- BidirectionalCollection

- Collection

- RandomAccessCollection

- Sequence


---
source: https://developer.apple.com/documentation/SwiftUI/ForEachSubviewCollection
crawled: 2025-12-02T17:40:10Z
---

# ForEachSubviewCollection

**Structure**

A collection which allows a view to be treated as a collection of its subviews in a for each loop.

## Declaration

```swift
struct ForEachSubviewCollection<Content> where Content : View
```

## Iterating over dynamic data

- **ForEach**: A structure that computes views on demand from an underlying collection of identified data.
- **ForEachSectionCollection**: A collection which allows a view to be treated as a collection of its sections in a for each loop.
- **DynamicViewContent**: A type of view that generates views from an underlying collection of data.

## Conforms To

- BidirectionalCollection
- Collection
- RandomAccessCollection
- Sequence

