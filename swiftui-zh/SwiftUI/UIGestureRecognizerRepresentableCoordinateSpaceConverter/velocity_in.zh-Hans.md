---
来源： https://developer.apple.com/documentation/SwiftUI/UIGestureRecognizerRepresentableCoordinateSpaceConverter/velocity(in:)
抓取时间： 2025-12-01T11:50:11Z
---

# velocity(in:)

**实例方法**

将所代表手势识别器的当前速度转换为手势识别器所连接视图的祖先的 SwiftUI 坐标空间。

## 声明

```swift
func velocity(in coordinateSpace: some CoordinateSpaceProtocol) -> CGPoint?
```

## 参数

- **coordinateSpace**：要转换到的 SwiftUI 坐标空间。

## 讨论

如果手势识别器没有实现`velocityInView:`方法，则返回nil。


---
source: https://developer.apple.com/documentation/SwiftUI/UIGestureRecognizerRepresentableCoordinateSpaceConverter/velocity(in:)
crawled: 2025-12-01T11:50:11Z
---

# velocity(in:)

**Instance Method**

Converts the represented gesture recognizer’s current velocity to a SwiftUI coordinate space of an ancestor of the view the gesture recognizer is attached to.

## Declaration

```swift
func velocity(in coordinateSpace: some CoordinateSpaceProtocol) -> CGPoint?
```

## Parameters

- **coordinateSpace**: The SwiftUI coordinate space to convert to.

## Discussion

If the gesture recognizer does not implement a `velocityInView:` method, returns nil.

