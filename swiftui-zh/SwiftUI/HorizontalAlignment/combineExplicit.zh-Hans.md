--- 来源：https://developer.apple.com/documentation/SwiftUI/HorizontalAlignment/combineExplicit(_:)

抓取时间：2025-12-03T06:36:42Z

---

# combineExplicit(_:)

**实例方法**

合并此实例生成的一系列显式对齐值。

## 声明

```swift
func combineExplicit<S>(_ values: S) -> CGFloat? where S : Sequence, S.Element == CGFloat?
```

## 说明

对于内置的水平对齐类型，此方法返回所有非 `nil` 值的平均值。

## 创建自定义对齐

- **init(_:)**：创建指定类型的自定义水平对齐。


---
source: https://developer.apple.com/documentation/SwiftUI/HorizontalAlignment/combineExplicit(_:)
crawled: 2025-12-03T06:36:42Z
---

# combineExplicit(_:)

**Instance Method**

Merges a sequence of explicit alignment values produced by this instance.

## Declaration

```swift
func combineExplicit<S>(_ values: S) -> CGFloat? where S : Sequence, S.Element == CGFloat?
```

## Discussion

For built-in horizontal alignment types, this method returns the mean of all non-`nil` values.

## Creating a custom alignment

- **init(_:)**: Creates a custom horizontal alignment of the specified type.

