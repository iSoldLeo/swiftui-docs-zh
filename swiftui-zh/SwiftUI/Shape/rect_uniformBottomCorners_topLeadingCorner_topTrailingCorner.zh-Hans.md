---
source: https://developer.apple.com/documentation/SwiftUI/Shape/rect(uniformBottomCorners:topLeadingCorner:topTrailingCorner:)
抓取时间： 2025-12-02T21:42:09Z
---

# rect(uniformBottomCorners:topLeadingCorner:topTrailingCorner:)

**类型方法**

在视图框架内对齐的矩形。角样式将统一应用于底部的两个角，而顶部的两个角则各有一个单独的角样式。

## 声明

```swift
static func rect(uniformBottomCorners: Edge.Corner.Style, topLeadingCorner: Edge.Corner.Style, topTrailingCorner: Edge.Corner.Style) -> Self
```

## 参数

- **uniformBottomCorners**：统一应用于底部两个角的角样式。此形状将首先单独解析两个角，然后从两个角中选取最大的解析半径并均匀应用，以实现对称外观。
- **topLeadingCorner**：顶部引导角样式。
- **topTrailingCorner**：顶部尾角样式。


---
source: https://developer.apple.com/documentation/SwiftUI/Shape/rect(uniformBottomCorners:topLeadingCorner:topTrailingCorner:)
crawled: 2025-12-02T21:42:09Z
---

# rect(uniformBottomCorners:topLeadingCorner:topTrailingCorner:)

**Type Method**

A rectangle shape that is aligned inside the frame of the view containing it. A corner style will be uniformly applied to the bottom two corners, while the top two corners will each has an indivdual corner style.

## Declaration

```swift
static func rect(uniformBottomCorners: Edge.Corner.Style, topLeadingCorner: Edge.Corner.Style, topTrailingCorner: Edge.Corner.Style) -> Self
```

## Parameters

- **uniformBottomCorners**: The corner style to be applied on the bottom two corners uniformly. This shape will first resolve the two corners individually, then pick the largest resolved radius out of the two and apply it uniformly to achieve the symmetric look.
- **topLeadingCorner**: The top leading corner style.
- **topTrailingCorner**: The top trailing corner style.

