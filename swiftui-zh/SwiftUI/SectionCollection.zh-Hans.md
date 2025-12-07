---
来源： https://developer.apple.com/documentation/SwiftUI/SectionCollection
抓取时间： 2025-12-02T17:40:07Z
---

# 节收集

**Structure**

表示视图部分的不透明集合。

## 声明

```swift
struct SectionCollection
```

## 概览

各部分都是按需构建的，因此只需访问该集合中创建内容所需的部分即可。

您可以使用 `Group/init(sectionsOf:transform:)` 初始化器访问视图的 [SectionCollection](SectionCollection.zh-Hans.md)。

给定视图中未明确指定为部分的任何内容都会与其同级内容组合成隐式部分，这意味着`SectionCollection` 中的部分数量最少为一个。

## 将视图组织成章节

- **Section**：容器视图，可用于在某些视图中添加层次结构。
- **SectionConfiguration**：指定节的内容。

## 符合

- 双向集合
- 集合
- 随机访问集合
- 序列


---
source: https://developer.apple.com/documentation/SwiftUI/SectionCollection
crawled: 2025-12-02T17:40:07Z
---

# SectionCollection

**Structure**

An opaque collection representing the sections of view.

## Declaration

```swift
struct SectionCollection
```

## Overview

Sections are constructed lazily, on demand, so access only as much of this collection as is necessary to create the resulting content.

You can get access to a view’s [SectionCollection](SectionCollection.zh-Hans.md) by using the `Group/init(sectionsOf:transform:)` initializer.

Any content of the given view which is not explicitly specified as a section is grouped with its sibling content to form implicit sections, meaning the minimum number of sections in a `SectionCollection` is one.

## Organizing views into sections

- **Section**: A container view that you can use to add hierarchy within certain views.
- **SectionConfiguration**: Specifies the contents of a section.

## Conforms To

- BidirectionalCollection
- Collection
- RandomAccessCollection
- Sequence

