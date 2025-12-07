---
来源： https://developer.apple.com/documentation/SwiftUI/UIGestureRecognizerRepresentableCoordinateSpaceConverter/localVelocity
抓取时间： 2025-12-03T07:00:58Z
---

# 本地速度

**实例属性**

所代表的手势识别器在其所连接的 SwiftUI 视图坐标空间中的当前速度。

## 声明

```swift
var localVelocity: CGPoint? { get }
```

## 讨论

如果手势识别器没有实现`velocityInView:`方法，则返回 nil。


---
source: https://developer.apple.com/documentation/SwiftUI/UIGestureRecognizerRepresentableCoordinateSpaceConverter/localVelocity
crawled: 2025-12-03T07:00:58Z
---

# localVelocity

**Instance Property**

The represented gesture recognizer’s current velocity in the coordinate space of the SwiftUI view it’s attached to.

## Declaration

```swift
var localVelocity: CGPoint? { get }
```

## Discussion

If the gesture recognizer does not implement a `velocityInView:` method, returns nil.

