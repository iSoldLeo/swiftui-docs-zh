---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/ClipOptions/inverse
抓取时间： 2025-12-03T17:20:03Z
---

# 逆

**类型属性**

反转形状或图层 alpha 作为剪辑蒙版的选项。

## 声明

```swift
static var inverse: GraphicsContext.ClipOptions { get }
```

## 讨论

使用此选项时，SwiftUI 将使用 `1 - alpha` 而不是 `alpha` 来处理给定的剪辑形状。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/ClipOptions/inverse
crawled: 2025-12-03T17:20:03Z
---

# inverse

**Type Property**

An option to invert the shape or layer alpha as the clip mask.

## Declaration

```swift
static var inverse: GraphicsContext.ClipOptions { get }
```

## Discussion

When you use this option, SwiftUI uses `1 - alpha` instead of `alpha` for the given clip shape.

