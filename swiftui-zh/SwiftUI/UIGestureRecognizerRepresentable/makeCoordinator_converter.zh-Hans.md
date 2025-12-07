--- 来源：https://developer.apple.com/documentation/SwiftUI/UIGestureRecognizerRepresentable/makeCoordinator(converter:)

抓取时间：2025-12-03T07:00:51Z

---

# makeCoordinator(converter:)

**实例方法**

创建自定义对象，用于将手势识别器的状态更改传递给 SwiftUI 界面的其他部分。

## 声明

```swift
@MainActor @preconcurrency func makeCoordinator(converter: Self.CoordinateSpaceConverter) -> Self.Coordinator
```

## 参数

- **converter**：用于在关联的 SwiftUI 视图层次结构中将位置转换为坐标空间/从坐标空间转换位置的结构。

## 说明

您可以通过传递给此协议中其他方法的 `Context` 来访问生成的协调器。


---
source: https://developer.apple.com/documentation/SwiftUI/UIGestureRecognizerRepresentable/makeCoordinator(converter:)
crawled: 2025-12-03T07:00:51Z
---

# makeCoordinator(converter:)

**Instance Method**

Creates the custom object that you use to communicate state changes from your gesture recognizer to other parts of your SwiftUI interface.

## Declaration

```swift
@MainActor @preconcurrency func makeCoordinator(converter: Self.CoordinateSpaceConverter) -> Self.Coordinator
```

## Parameters

- **converter**: A structure used to convert locations  to/from coordinate spaces in the hierarchy of the associated SwiftUI view.

## Discussion

You access the resulting coordinator via the `Context` passed into other methods in this protocol.

