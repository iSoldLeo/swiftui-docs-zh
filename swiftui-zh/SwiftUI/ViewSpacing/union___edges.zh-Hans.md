---
来源： https://developer.apple.com/documentation/SwiftUI/ViewSpacing/union(_:edges:)
抓取时间：2025-12-03T06:39:34Z


# union(_:edges:)

**实例方法**

获取一个新值，将另一个间距实例的间距首选项与此实例的指定边缘集合并。

## 声明

```swift
func union(_ other: ViewSpacing, edges: Edge.Set = .all) -> ViewSpacing
```

## 参数

- **other**：另一个要与本例合并的间距首选项实例。
- **edges**：要合并的边。未指定的边在方法完成后保持不变。

## 返回值

包含合并值的新视图间距偏好设置实例。

## 讨论

此方法的行为类似于[formUnion(_:edges:)](formUnion___edges.zh-Hans.md)，不同之处在于它在合并前会创建原始间距首选项实例的副本，而不会修改原始实例。

## 合并间距实例

- **formUnion(_:edges:)**：针对指定的边集，将另一个间距实例的间距首选项与此实例合并。


---
source: https://developer.apple.com/documentation/SwiftUI/ViewSpacing/union(_:edges:)
crawled: 2025-12-03T06:39:34Z
---

# union(_:edges:)

**Instance Method**

Gets a new value that merges the spacing preferences of another spacing instance with this instance for a specified set of edges.

## Declaration

```swift
func union(_ other: ViewSpacing, edges: Edge.Set = .all) -> ViewSpacing
```

## Parameters

- **other**: Another spacing preferences instance to merge with this one.
- **edges**: The edges to merge. Edges that you don’t specify are unchanged after the method completes.

## Return Value

A new view spacing preferences instance with the merged values.

## Discussion

This method behaves like [formUnion(_:edges:)](formUnion___edges.zh-Hans.md), except that it creates a copy of the original spacing preferences instance before merging, leaving the original instance unmodified.

## Merging spacing instances

- **formUnion(_:edges:)**: Merges the spacing preferences of another spacing instance with this instance for a specified set of edges.

