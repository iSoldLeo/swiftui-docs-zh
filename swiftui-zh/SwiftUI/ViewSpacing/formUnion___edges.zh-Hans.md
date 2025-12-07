---
来源： https://developer.apple.com/documentation/SwiftUI/ViewSpacing/formUnion(_:edges:)
抓取时间：2025-12-03T06:39:33Z


# formUnion(_:edges:)

**实例方法**

针对指定的边缘集，将另一个间距实例的间距首选项与本实例的间距首选项合并。

## 声明

```swift
mutating func formUnion(_ other: ViewSpacing, edges: Edge.Set = .all)
```

## 参数

- **other**：与本例合并的另一个间距优选实例。
- **edges**：要合并的边。未指定的边在方法完成后保持不变。

### 讨论

当你将另一个间距首选项实例与此实例合并时，此实例最终会在每一条指定的边上使用其原始值或另一个实例的值中较大的值。您可以使用集合中的每个值重复调用该方法，以合并偏好集合。合并的结果是每条边上满足该边所有输入中最大要求的最小偏好值。

如果您想在不修改原始实例的情况下合并首选项，请使用 [union(_:edges:)](union___edges.zh-Hans.md) 代替。

## 合并间距实例

- **union(_:edges:)**：获取一个新值，用于将另一个间距实例的间距首选项与此实例的指定边集合并。


---
source: https://developer.apple.com/documentation/SwiftUI/ViewSpacing/formUnion(_:edges:)
crawled: 2025-12-03T06:39:33Z
---

# formUnion(_:edges:)

**Instance Method**

Merges the spacing preferences of another spacing instance with this instance for a specified set of edges.

## Declaration

```swift
mutating func formUnion(_ other: ViewSpacing, edges: Edge.Set = .all)
```

## Parameters

- **other**: Another spacing preferences instances to merge with this one.
- **edges**: The edges to merge. Edges that you don’t specify are unchanged after the method completes.

## Discussion

When you merge another spacing preference instance with this one, this instance ends up with the greater of its original value or the other instance’s value for each of the specified edges. You can call the method repeatedly with each value in a collection to merge a collection of preferences. The result has the smallest preferences on each edge that meets the largest requirements of all the inputs for that edge.

If you want to merge preferences without modifying the original instance, use [union(_:edges:)](union___edges.zh-Hans.md) instead.

## Merging spacing instances

- **union(_:edges:)**: Gets a new value that merges the spacing preferences of another spacing instance with this instance for a specified set of edges.

