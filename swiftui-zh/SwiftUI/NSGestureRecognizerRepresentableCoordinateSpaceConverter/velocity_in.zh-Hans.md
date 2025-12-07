---
来源： https://developer.apple.com/documentation/SwiftUI/NSGestureRecognizerRepresentableCoordinateSpaceConverter/velocity(in:)
抓取时间： 2025-12-01T11:47:25Z
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

## 返回值

所代表的手势识别器当前速度转换为给定的 `coordinateSpace`，如果所代表的手势识别器不响应 `-velocityInView:`选择器，则转换为 `nil`。


---
source: https://developer.apple.com/documentation/SwiftUI/NSGestureRecognizerRepresentableCoordinateSpaceConverter/velocity(in:)
crawled: 2025-12-01T11:47:25Z
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

## Return Value

The represented gesture recognizer’s current velocity converted to the given `coordinateSpace`, or `nil` if the represented gesture recognizer doesn’t respond to `-velocityInView:` selector.

