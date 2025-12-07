---
来源： https://developer.apple.com/documentation/SwiftUI/NSGestureRecognizerRepresentableCoordinateSpaceConverter/location(in:)
抓取时间： 2025-12-01T11:47:24Z
---

# location(in:)

**实例方法**

将所代表手势识别器的当前位置转换为手势识别器所连接视图的祖先的 SwiftUI 坐标空间。

### 声明

```swift
func location(in coordinateSpace: some CoordinateSpaceProtocol) -> CGPoint
```

## 参数

- **coordinateSpace**：要转换到的 SwiftUI 坐标空间。

## 返回值

将所代表的手势识别器当前位置转换为给定的`coordinateSpace`。


---
source: https://developer.apple.com/documentation/SwiftUI/NSGestureRecognizerRepresentableCoordinateSpaceConverter/location(in:)
crawled: 2025-12-01T11:47:24Z
---

# location(in:)

**Instance Method**

Converts the represented gesture recognizer’s current location to a SwiftUI coordinate space of an ancestor of the view the gesture recognizer is attached to.

## Declaration

```swift
func location(in coordinateSpace: some CoordinateSpaceProtocol) -> CGPoint
```

## Parameters

- **coordinateSpace**: The SwiftUI coordinate space to convert to.

## Return Value

The represrnted gesture recognizer’s current location converted into the given `coordinateSpace`.

