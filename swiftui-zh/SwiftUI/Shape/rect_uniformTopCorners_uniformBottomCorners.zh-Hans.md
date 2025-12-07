---
来源： https://developer.apple.com/documentation/SwiftUI/Shape/rect(uniformTopCorners:uniformBottomCorners:)
抓取时间：2025-12-01T02:33:08Z
---

# rect(uniformTopCorners:uniformBottomCorners:)

**类型方法**

在视图框架内对齐的矩形。一种角样式将统一应用于顶部的两个角，而另一种角样式将统一应用于底部的两个角。

## 声明

```swift
static func rect(uniformTopCorners: Edge.Corner.Style, uniformBottomCorners: Edge.Corner.Style) -> Self
```

## 参数

- **uniformTopCorners**：统一应用于顶部两个角的角样式。此形状将首先单独解析两个角，然后从两个角中选取最大的解析半径并均匀应用，以实现对称外观。
- **uniformBottomCorners**：统一应用于底部两个角的角样式。此形状将首先单独解析两个角，然后从两个角中选取最大的解析半径并均匀应用，以实现对称外观。


---
source: https://developer.apple.com/documentation/SwiftUI/Shape/rect(uniformTopCorners:uniformBottomCorners:)
crawled: 2025-12-01T02:33:08Z
---

# rect(uniformTopCorners:uniformBottomCorners:)

**Type Method**

A rectangle shape that is aligned inside the frame of the view containing it. A corner style will be uniformly applied to the top two corners, while another corner style will be uniformly applied to the bottom two.

## Declaration

```swift
static func rect(uniformTopCorners: Edge.Corner.Style, uniformBottomCorners: Edge.Corner.Style) -> Self
```

## Parameters

- **uniformTopCorners**: The corner style to be applied on the top two corners uniformly. This shape will first resolve the two corners individually, then pick the largest resolved radius out of the two and apply it uniformly to achieve the symmetric look.
- **uniformBottomCorners**: The corner style to be applied on the bottom two corners uniformly. This shape will first resolve the two corners individually, then pick the largest resolved radius out of the two and apply it uniformly to achieve the symmetric look.

