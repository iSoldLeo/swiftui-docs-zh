---
source: https://developer.apple.com/documentation/SwiftUI/Shape/rect(uniformLeadingCorners:topTrailingCorner:bottomTrailingCorner:)
抓取时间：2025-12-02T21:42:10Z
---

# rect(uniformLeadingCorners:topTrailingCorner:bottomTrailingCorner:)

**类型方法**

在视图框架内对齐的矩形。角样式将统一应用于前两个角，而后两个角则各有一个单独的角样式。

## 声明

```swift
static func rect(uniformLeadingCorners: Edge.Corner.Style, topTrailingCorner: Edge.Corner.Style, bottomTrailingCorner: Edge.Corner.Style) -> Self
```

## 参数

- **uniformLeadingCorners**：要统一应用于前两个角的角样式。此形状将首先单独解析两个角，然后从两个角中选取最大的解析半径并均匀应用，以实现对称外观。
- **topTrailingCorner**：顶部尾角样式。
- **bottomTrailingCorner**：下斜角样式。


---
source: https://developer.apple.com/documentation/SwiftUI/Shape/rect(uniformLeadingCorners:topTrailingCorner:bottomTrailingCorner:)
crawled: 2025-12-02T21:42:10Z
---

# rect(uniformLeadingCorners:topTrailingCorner:bottomTrailingCorner:)

**Type Method**

A rectangle shape that is aligned inside the frame of the view containing it. A corner style will be uniformly applied to the leading two corners, while the trailing two corners will each has an indivdual corner style.

## Declaration

```swift
static func rect(uniformLeadingCorners: Edge.Corner.Style, topTrailingCorner: Edge.Corner.Style, bottomTrailingCorner: Edge.Corner.Style) -> Self
```

## Parameters

- **uniformLeadingCorners**: The corner style to be applied on the leading two corners uniformly. This shape will first resolve the two corners individually, then pick the largest resolved radius out of the two and apply it uniformly to achieve the symmetric look.
- **topTrailingCorner**: The top trailing corner style.
- **bottomTrailingCorner**: The bottom trailing corner style.

