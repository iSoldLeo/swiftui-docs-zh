---
来源： https://developer.apple.com/documentation/SwiftUI/NSGestureRecognizerRepresentableCoordinateSpaceConverter/localVelocity
抓取时间： 2025-12-03T06:58:10Z
---

# 本地速度

**实例属性**

所代表的手势识别器在其所连接的 SwiftUI 视图坐标空间中的当前速度，如果所代表的手势识别器不响应`-velocityInView:` 选择器，则为`nil`。

### 声明

```swift
var localVelocity: CGPoint? { get }
```


---
source: https://developer.apple.com/documentation/SwiftUI/NSGestureRecognizerRepresentableCoordinateSpaceConverter/localVelocity
crawled: 2025-12-03T06:58:10Z
---

# localVelocity

**Instance Property**

The represented gesture recognizer’s current velocity in the coordinate space of the SwiftUI view it’s attached to, or `nil` if the represented gesture recognizer doesn’t respond to `-velocityInView:` selector.

## Declaration

```swift
var localVelocity: CGPoint? { get }
```

