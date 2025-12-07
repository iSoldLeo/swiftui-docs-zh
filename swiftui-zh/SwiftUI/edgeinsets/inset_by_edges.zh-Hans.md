--- 来源：https://developer.apple.com/documentation/SwiftUI/EdgeInsets/inset(by:edges:)

抓取时间：2025-12-03T06:39:17Z

---

# inset(by:edges:)

**实例方法**

返回一个内边距，该内边距已根据指定边的角尺寸进行调整。当指定边的两个角内边距值不同时，将使用较大的内边距值。例如，如果指定了顶部边，则顶部内边距将根据顶部前角和后角内边距中较大的值进行调整。

## 声明

```swift
func inset(by corners: RectangleCornerInsets, edges: Edge.Set = .all) -> EdgeInsets
```

## 参数

- **corners**：要添加到内边距的角尺寸。

- **edges**：要添加到内嵌图中的角边集合。


---
source: https://developer.apple.com/documentation/SwiftUI/EdgeInsets/inset(by:edges:)
crawled: 2025-12-03T06:39:17Z
---

# inset(by:edges:)

**Instance Method**

Returns an inset that has been modified by the corner sizes in the specified edges. When two corner insets diverge in their values for the specified edge, the maximum inset value will be used. For example, when the top edge is specified, the top inset will be adjusted by the larger of the two heights from the top leading and trailing corner inset sizes.

## Declaration

```swift
func inset(by corners: RectangleCornerInsets, edges: Edge.Set = .all) -> EdgeInsets
```

## Parameters

- **corners**: The corner sizes to add to the insets.
- **edges**: The set of corner edges which should be added to the insets.

