--- 来源：https://developer.apple.com/documentation/SwiftUI/NSGestureRecognizerRepresentableContext

抓取时间：2025-12-02T17:44:47Z

---

# NSGestureRecognizerRepresentableContext

**Structure**

用于创建和更新表示手势识别器的系统状态上下文信息。

## 声明

```swift
struct NSGestureRecognizerRepresentableContext<Representable> where Representable : NSGestureRecognizerRepresentable
```

## 实例属性

- **converter**：用于在关联的 SwiftUI 视图层次结构中将位置转换为坐标空间或从坐标空间转换位置的结构。

- **coordinator**：用于将手势识别器的状态更改传递给 SwiftUI 界面其他部分的自定义对象。

## 将 AppKit 手势识别器添加到 SwiftUI 视图层级结构中

- **NSGestureRecognizerRepresentable**：一个用于封装 `NSGestureRecognizer` 的包装器，用于将该手势识别器集成到 SwiftUI 视图层级结构中。

- **NSGestureRecognizerRepresentableCoordinateSpaceConverter**：一个用于在与 [NSGestureRecognizerRepresentable](NSGestureRecognizerRepresentable.zh-Hans.md) 关联的 SwiftUI 视图层级结构中，将位置转换为坐标空间或从坐标空间转换位置的结构。


---
source: https://developer.apple.com/documentation/SwiftUI/NSGestureRecognizerRepresentableContext
crawled: 2025-12-02T17:44:47Z
---

# NSGestureRecognizerRepresentableContext

**Structure**

Contextual information about the state of the system that you use to create and update a represented gesture recognizer.

## Declaration

```swift
struct NSGestureRecognizerRepresentableContext<Representable> where Representable : NSGestureRecognizerRepresentable
```

## Instance Properties

- **converter**: A structure used to convert locations to and from coordinate spaces in the hierarchy of the associated SwiftUI view.
- **coordinator**: The custom object that you use to communicate state changes from your gesture recognizer to other parts of your SwiftUI interface.

## Adding AppKit gesture recognizers into SwiftUI view hierarchies

- **NSGestureRecognizerRepresentable**: A wrapper for an `NSGestureRecognizer` that you use to integrate that gesture recognizer into your SwiftUI hierarchy.
- **NSGestureRecognizerRepresentableCoordinateSpaceConverter**: A structure used to convert locations to and from coordinate spaces in the hierarchy of the SwiftUI view associated with an [NSGestureRecognizerRepresentable](NSGestureRecognizerRepresentable.zh-Hans.md).

