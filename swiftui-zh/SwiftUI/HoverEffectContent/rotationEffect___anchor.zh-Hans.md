--- 来源：https://developer.apple.com/documentation/SwiftUI/HoverEffectContent/rotationEffect(_:anchor:)

抓取时间：2025-12-03T06:45:54Z

---

# rotationEffect(_:anchor:)

**实例方法**

围绕指定点在二维平面上旋转内容。

## 声明

```swift
func rotationEffect(_ angle: Angle, anchor: UnitPoint = .center) -> some HoverEffectContent

```

## 参数

- **angle**：内容旋转的角度。

- **anchor**：内容中用于旋转的单位点。默认值为 [center](../UnitPoint/center.zh-Hans.md)。

## 返回值

旋转效果。

## 说明

此效果围绕指向 xy 平面外的轴旋转内容。它不会影响内容的显示框架。


---
source: https://developer.apple.com/documentation/SwiftUI/HoverEffectContent/rotationEffect(_:anchor:)
crawled: 2025-12-03T06:45:54Z
---

# rotationEffect(_:anchor:)

**Instance Method**

Rotates content in two dimensions around the specified point.

## Declaration

```swift
func rotationEffect(_ angle: Angle, anchor: UnitPoint = .center) -> some HoverEffectContent

```

## Parameters

- **angle**: The angle by which to rotate the content.
- **anchor**: A unit point within the content about which to perform the rotation. The default value is [center](../UnitPoint/center.zh-Hans.md).

## Return Value

A rotation effect.

## Discussion

This effect rotates the content around the axis that points out of the xy-plane. It has no effect on the content’s frame.

