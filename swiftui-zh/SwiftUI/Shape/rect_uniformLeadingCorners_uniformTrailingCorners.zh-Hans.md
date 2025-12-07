---
来源： https://developer.apple.com/documentation/SwiftUI/Shape/rect(uniformLeadingCorners:uniformTrailingCorners:)
抓取时间：2025-12-02T21:42:11Z
---

# rect(uniformLeadingCorners:uniformTrailingCorners:)

**类型方法**

在视图框架内对齐的矩形。一种边角样式将统一应用于前边的两个角，而另一种边角样式将统一应用于后边的两个角。

## 声明

```swift
static func rect(uniformLeadingCorners: Edge.Corner.Style, uniformTrailingCorners: Edge.Corner.Style) -> Self
```

## 参数

- **uniformLeadingCorners**：要统一应用于前两个角的角样式。此形状将首先单独解析两个角，然后从两个角中选取最大的解析半径并均匀应用，以实现对称外观。
- **uniformTrailingCorners**：统一应用于尾部两个角的角样式。此形状将首先单独解析两个角，然后从两个角中选取最大的解析半径并均匀应用，以实现对称外观。


---
source: https://developer.apple.com/documentation/SwiftUI/Shape/rect(uniformLeadingCorners:uniformTrailingCorners:)
crawled: 2025-12-02T21:42:11Z
---

# rect(uniformLeadingCorners:uniformTrailingCorners:)

**Type Method**

A rectangle shape that is aligned inside the frame of the view containing it. A corner style will be uniformly applied to the leading two corners, while another corner style will be uniformly applied to the trailing two.

## Declaration

```swift
static func rect(uniformLeadingCorners: Edge.Corner.Style, uniformTrailingCorners: Edge.Corner.Style) -> Self
```

## Parameters

- **uniformLeadingCorners**: The corner style to be applied on the leading two corners uniformly. This shape will first resolve the two corners individually, then pick the largest resolved radius out of the two and apply it uniformly to achieve the symmetric look.
- **uniformTrailingCorners**: The corner style to be applied on the trailing two corners uniformly. This shape will first resolve the two corners individually, then pick the largest resolved radius out of the two and apply it uniformly to achieve the symmetric look.

