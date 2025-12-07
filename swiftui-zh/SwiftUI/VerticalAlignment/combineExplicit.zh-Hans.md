--- 来源：https://developer.apple.com/documentation/SwiftUI/VerticalAlignment/combineExplicit(_:)

抓取时间：2025-12-01T11:25:59Z

---

# combineExplicit(_:)

**实例方法**

合并此实例生成的一系列显式对齐值。

## 声明

```swift
func combineExplicit<S>(_ values: S) -> CGFloat? where S : Sequence, S.Element == CGFloat?
```

## 说明

对于大多数对齐类型，此方法返回所有非 `nil` 值的平均值。但是，某些类型使用其他规则。例如，[firstTextBaseline](firstTextBaseline.zh-Hans.md) 返回最小值，而 [lastTextBaseline](lastTextBaseline.zh-Hans.md) 返回最大值。

## 创建自定义对齐

- **init(_:)**：创建指定类型的自定义垂直对齐。


---
source: https://developer.apple.com/documentation/SwiftUI/VerticalAlignment/combineExplicit(_:)
crawled: 2025-12-01T11:25:59Z
---

# combineExplicit(_:)

**Instance Method**

Merges a sequence of explicit alignment values produced by this instance.

## Declaration

```swift
func combineExplicit<S>(_ values: S) -> CGFloat? where S : Sequence, S.Element == CGFloat?
```

## Discussion

For most alignment types, this method returns the mean of all non-`nil` values. However, some types use other rules. For example, [firstTextBaseline](firstTextBaseline.zh-Hans.md) returns the minimum value, while [lastTextBaseline](lastTextBaseline.zh-Hans.md) returns the maximum value.

## Creating a custom alignment

- **init(_:)**: Creates a custom vertical alignment of the specified type.

