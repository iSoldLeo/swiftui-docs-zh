---
来源： https://developer.apple.com/documentation/SwiftUI/UIGestureRecognizerRepresentableCoordinateSpaceConverter/convert(globalPoint:to:)
抓取时间：2025-12-03T07:00:59Z
---

# convert(globalPoint:to:)

**实例方法**

将全局坐标空间中的一个点转换为手势识别器所连接视图的祖先的 SwiftUI 坐标空间。

### 声明

```swift
func convert(globalPoint: CGPoint, to coordinateSpace: some CoordinateSpaceProtocol = .local) -> CGPoint
```

## 参数

- **globalPoint**：全局坐标空间中的点。
- **coordinateSpace**：要转换到的 SwiftUI 坐标空间。


---
source: https://developer.apple.com/documentation/SwiftUI/UIGestureRecognizerRepresentableCoordinateSpaceConverter/convert(globalPoint:to:)
crawled: 2025-12-03T07:00:59Z
---

# convert(globalPoint:to:)

**Instance Method**

Converts a point in the global coordinate space to a SwiftUI coordinate space of an ancestor of the view the gesture recognizer is attached to.

## Declaration

```swift
func convert(globalPoint: CGPoint, to coordinateSpace: some CoordinateSpaceProtocol = .local) -> CGPoint
```

## Parameters

- **globalPoint**: The point in the global coordinate space.
- **coordinateSpace**: The SwiftUI coordinate space to convert to.

