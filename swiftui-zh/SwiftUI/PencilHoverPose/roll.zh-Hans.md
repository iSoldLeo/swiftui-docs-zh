--- 来源：https://developer.apple.com/documentation/SwiftUI/PencilHoverPose/roll

抓取时间：2025-12-03T06:43:53Z

---

# roll

**实例属性**

表示 Apple Pencil 悬停时的滚动角度。

## 声明

```swift
let roll: Angle
```

## 说明

当用户开始使用 Apple Pencil 时，此值为 `.zero`，并随着用户沿笔杆滚动 Apple Pencil 而相对于初始角度变化。如果 Apple Pencil 不支持检测其滚动角度，则此属性始终为 `.zero`。


---
source: https://developer.apple.com/documentation/SwiftUI/PencilHoverPose/roll
crawled: 2025-12-03T06:43:53Z
---

# roll

**Instance Property**

A value that represents the barrel roll angle of the hovering Apple Pencil.

## Declaration

```swift
let roll: Angle
```

## Discussion

This value is `.zero` when the user starts using their Apple Pencil, and changes relative to that initial angle as the user rolls the Apple Pencil alongside its barrel. If the Apple Pencil doesn’t support detecting its barrel roll angle, this property is always `.zero`.

