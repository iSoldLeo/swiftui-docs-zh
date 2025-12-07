---
来源：https://developer.apple.com/documentation/SwiftUI/Shape/rect(UniformTopCorners:bottomLeadingCorner:bottomTrailingCorner:)
抓取时间：2025-12-01T02:33:08Z
---

# rect(uniformTopCorners:bottomLeadingCorner:bottomTrailingCorner:)

**类型方法**

在视图框架内对齐的矩形。顶部两个角将统一使用一种角样式，而底部两个角则各有一种独立的角样式。

## 声明

```swift
static func rect(uniformTopCorners: Edge.Corner.Style, bottomLeadingCorner: Edge.Corner.Style, bottomTrailingCorner: Edge.Corner.Style) -> Self
```

## 参数

- **uniformTopCorners**：统一应用于顶部两个角的角样式。此形状将首先单独解析两个角，然后从两个角中选取最大的解析半径并均匀应用，以实现对称外观。
- **bottomLeadingCorner**：底部前角样式。
- **bottomTrailingCorner**：底部拖尾角样式。


---
source: https://developer.apple.com/documentation/SwiftUI/Shape/rect(uniformTopCorners:bottomLeadingCorner:bottomTrailingCorner:)
crawled: 2025-12-01T02:33:08Z
---

# rect(uniformTopCorners:bottomLeadingCorner:bottomTrailingCorner:)

**Type Method**

A rectangle shape that is aligned inside the frame of the view containing it. A corner style will be uniformly applied to the top two corners, while the bottom two corners will each has an indivdual corner style.

## Declaration

```swift
static func rect(uniformTopCorners: Edge.Corner.Style, bottomLeadingCorner: Edge.Corner.Style, bottomTrailingCorner: Edge.Corner.Style) -> Self
```

## Parameters

- **uniformTopCorners**: The corner style to be applied on the top two corners uniformly. This shape will first resolve the two corners individually, then pick the largest resolved radius out of the two and apply it uniformly to achieve the symmetric look.
- **bottomLeadingCorner**: The bottom leading corner style.
- **bottomTrailingCorner**: The bottom trailing corner style.

