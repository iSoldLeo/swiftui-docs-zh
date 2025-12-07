---
source: https://developer.apple.com/documentation/SwiftUI/Shape/rect(uniformTrailingCorners:topLeadingCorner:bottomLeadingCorner:)
抓取时间：2025-12-01T02:33:09Z
---

# rect(uniformTrailingCorners:topLeadingCorner:bottomLeadingCorner:)

**类型方法**

在视图框架内对齐的矩形。一个角样式将统一应用于尾部的两个角，而前部的两个角则各有一个独立的角样式。

## 声明

```swift
static func rect(uniformTrailingCorners: Edge.Corner.Style, topLeadingCorner: Edge.Corner.Style, bottomLeadingCorner: Edge.Corner.Style) -> Self
```

## 参数

- **uniformTrailingCorners**：统一应用于尾部两个角的角样式。此形状将首先单独解析两个角，然后从两个角中选取最大的解析半径并均匀应用，以实现对称外观。
- **topLeadingCorner**：顶部引导角样式。
- **bottomLeadingCorner**：下引角样式。


---
source: https://developer.apple.com/documentation/SwiftUI/Shape/rect(uniformTrailingCorners:topLeadingCorner:bottomLeadingCorner:)
crawled: 2025-12-01T02:33:09Z
---

# rect(uniformTrailingCorners:topLeadingCorner:bottomLeadingCorner:)

**Type Method**

A rectangle shape that is aligned inside the frame of the view containing it. A corner style will be uniformly applied to the trailing two corners, while the leading two corners will each has an indivdual corner style.

## Declaration

```swift
static func rect(uniformTrailingCorners: Edge.Corner.Style, topLeadingCorner: Edge.Corner.Style, bottomLeadingCorner: Edge.Corner.Style) -> Self
```

## Parameters

- **uniformTrailingCorners**: The corner style to be applied on the trailing two corners uniformly. This shape will first resolve the two corners individually, then pick the largest resolved radius out of the two and apply it uniformly to achieve the symmetric look.
- **topLeadingCorner**: The top leading corner style.
- **bottomLeadingCorner**: The bottom leading corner style.

