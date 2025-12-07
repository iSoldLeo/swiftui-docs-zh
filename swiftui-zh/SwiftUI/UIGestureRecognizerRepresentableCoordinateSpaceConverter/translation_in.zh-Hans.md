---
来源： https://developer.apple.com/documentation/SwiftUI/UIGestureRecognizerRepresentableCoordinateSpaceConverter/translation(in:)
抓取时间： 2025-12-01T11:50:10Z
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

## 讨论

如果手势识别器没有实现`translationInView:`方法，则返回nil。


---
source: https://developer.apple.com/documentation/SwiftUI/UIGestureRecognizerRepresentableCoordinateSpaceConverter/translation(in:)
crawled: 2025-12-01T11:50:10Z
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

## Discussion

If the gesture recognizer does not implement a `translationInView:` method, returns nil.

