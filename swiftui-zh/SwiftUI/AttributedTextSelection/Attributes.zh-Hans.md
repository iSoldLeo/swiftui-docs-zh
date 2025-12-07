---
来源： https://developer.apple.com/documentation/SwiftUI/AttributedTextSelection/Attributes
抓取时间： 2025-12-03T06:17:41Z
---

# AttributedTextSelection.Attributes

**Structure**

选区在特定文本中的所有属性值的序列。

### 声明

```swift
struct Attributes<Text>
```

## 概览

选区的值是完全选中或部分选中的每个运行的属性值，如果选区是插入点，则是键入属性。

默认情况下，序列包含每个运行的属性容器或键入属性。使用[Attributes](Attributes.zh-Hans.md)'下标可仅获取单个属性的值：

```swift
selection.attributes(in: text)[\.foregroundColor].contains(.red)
```

## 下标

- **subscript(_:)**：返回迭代单个属性值的序列。

## 符合

- 序列


---
source: https://developer.apple.com/documentation/SwiftUI/AttributedTextSelection/Attributes
crawled: 2025-12-03T06:17:41Z
---

# AttributedTextSelection.Attributes

**Structure**

A sequence of all attribute values a selection has in a certain text.

## Declaration

```swift
struct Attributes<Text>
```

## Overview

The values of a selection are the attribute values of each run that is fully or partially selected, or the typing attributes in the case the selection is an insertion point.

By default, the sequence contains the attribute container for every run or the typing attributes. Use the [Attributes](Attributes.zh-Hans.md)’ subscript to obtain only the values for a single attribute:

```swift
selection.attributes(in: text)[\.foregroundColor].contains(.red)
```

## Subscripts

- **subscript(_:)**: Returns a sequence which iterates of the values of a single attribute.

## Conforms To

- Sequence

