---
来源： https://developer.apple.com/documentation/SwiftUI/NSGestureRecognizerRepresentableCoordinateSpaceConverter
抓取时间： 2025-12-02T17:44:48Z
---

# NSGestureRecognizerRepresentableCoordinateSpaceConverter

**Structure**

用于在与[NSGestureRecognizerRepresentable](NSGestureRecognizerRepresentable.zh-Hans.md) 关联的 SwiftUI 视图的层次结构中将位置转换为坐标空间或从坐标空间转换为位置的结构。

## 声明

```swift
struct NSGestureRecognizerRepresentableCoordinateSpaceConverter
```

## 实例属性

- **localLocation**：所代表的手势识别器在其所连接的 SwiftUI 视图坐标空间中的当前位置。
- **localTranslation**：所代表的手势识别器在其所连接的 SwiftUI 视图的坐标空间中的当前平移位置，或者`nil`（如果所代表的手势识别器不响应`-translationInView:` 选择器）。
- **localVelocity**：所代表的手势识别器在其所连接的 SwiftUI 视图的坐标空间中的当前速度，或者`nil`（如果所代表的手势识别器不响应`-velocityInView:` 选择器）。

### 实例方法

- **convert(globalPoint:to:)**：将全局坐标空间中的一个点转换为手势识别器所连接视图的祖先的 SwiftUI 坐标空间。
- **location(in:)**：将所代表的手势识别器当前位置转换为手势识别器所连接视图的祖先的 SwiftUI 坐标空间。
- **translation(in:)**：将所代表手势识别器的当前平移转换为手势识别器所连接视图的祖先的 SwiftUI 坐标空间。
- **velocity(in:)**：将所代表手势识别器的当前速度转换为手势识别器所连接视图的祖先的 SwiftUI 坐标空间。

## 在 SwiftUI 视图层次中添加 AppKit 手势识别器

- **NSGestureRecognizerRepresentable**：`NSGestureRecognizer`的封装器，用于将手势识别器集成到 SwiftUI 层次结构中。
- **NSGestureRecognizerRepresentableContext**：有关系统状态的上下文信息，用于创建和更新所代表的手势识别器。


---
source: https://developer.apple.com/documentation/SwiftUI/NSGestureRecognizerRepresentableCoordinateSpaceConverter
crawled: 2025-12-02T17:44:48Z
---

# NSGestureRecognizerRepresentableCoordinateSpaceConverter

**Structure**

A structure used to convert locations to and from coordinate spaces in the hierarchy of the SwiftUI view associated with an [NSGestureRecognizerRepresentable](NSGestureRecognizerRepresentable.zh-Hans.md).

## Declaration

```swift
struct NSGestureRecognizerRepresentableCoordinateSpaceConverter
```

## Instance Properties

- **localLocation**: The represented gesture recognizer’s current location in the coordinate space of the SwiftUI view it’s attached to.
- **localTranslation**: The represented gesture recognizer’s current translation in the coordinate space of the SwiftUI view it’s attached to, or `nil` if the represented gesture recognizer doesn’t respond to `-translationInView:` selector.
- **localVelocity**: The represented gesture recognizer’s current velocity in the coordinate space of the SwiftUI view it’s attached to, or `nil` if the represented gesture recognizer doesn’t respond to `-velocityInView:` selector.

## Instance Methods

- **convert(globalPoint:to:)**: Converts a point in the global coordinate space to a SwiftUI coordinate space of an ancestor of the view the gesture recognizer is attached to.
- **location(in:)**: Converts the represented gesture recognizer’s current location to a SwiftUI coordinate space of an ancestor of the view the gesture recognizer is attached to.
- **translation(in:)**: Converts the represented gesture recognizer’s current translation to a SwiftUI coordinate space of an ancestor of the view the gesture recognizer is attached to.
- **velocity(in:)**: Converts the represented gesture recognizer’s current velocity to a SwiftUI coordinate space of an ancestor of the view the gesture recognizer is attached to.

## Adding AppKit gesture recognizers into SwiftUI view hierarchies

- **NSGestureRecognizerRepresentable**: A wrapper for an `NSGestureRecognizer` that you use to integrate that gesture recognizer into your SwiftUI hierarchy.
- **NSGestureRecognizerRepresentableContext**: Contextual information about the state of the system that you use to create and update a represented gesture recognizer.

