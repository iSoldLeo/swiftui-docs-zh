---
来源： https://developer.apple.com/documentation/SwiftUI/NSGestureRecognizerRepresentableCoordinateSpaceConverter/translation(in:)
抓取时间： 2025-12-03T06:58:13Z
---

# translation(in:)

**实例方法**

将所代表手势识别器的当前平移转换为手势识别器所连接视图的祖先的 SwiftUI 坐标空间。

### 声明

```swift
func translation(in coordinateSpace: some CoordinateSpaceProtocol) -> CGPoint?
```

## 参数

- **coordinateSpace**：要转换到的 SwiftUI 坐标空间。

## 返回值

所代表的手势识别器当前转换为给定的`coordinateSpace`，如果所代表的手势识别器不响应`-translationInView:`选择器，则转换为`nil`。


---
source: https://developer.apple.com/documentation/SwiftUI/NSGestureRecognizerRepresentableCoordinateSpaceConverter/translation(in:)
crawled: 2025-12-03T06:58:13Z
---

# translation(in:)

**Instance Method**

Converts the represented gesture recognizer’s current translation to a SwiftUI coordinate space of an ancestor of the view the gesture recognizer is attached to.

## Declaration

```swift
func translation(in coordinateSpace: some CoordinateSpaceProtocol) -> CGPoint?
```

## Parameters

- **coordinateSpace**: The SwiftUI coordinate space to convert to.

## Return Value

The represented gesture recognizer’s current translation converted to the given `coordinateSpace`, or `nil` if the represented gesture recognizer doesn’t respond to `-translationInView:` selector.

