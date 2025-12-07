--- 来源：https://developer.apple.com/documentation/SwiftUI/UIGestureRecognizerRepresentableCoordinateSpaceConverter
抓取时间：2025-12-02T17:44:58Z

---

# UIGestureRecognizerRepresentableCoordinateSpaceConverter

**Structure**

用于在与 [UIGestureRecognizerRepresentable](UIGestureRecognizerRepresentable.zh-Hans.md) 关联的 SwiftUI 视图层级结构中，将位置转换为坐标空间或从坐标空间转换位置的代理结构。

## 声明

```swift
struct UIGestureRecognizerRepresentableCoordinateSpaceConverter
```

## 实例属性

- **localLocation**：表示的手势识别器在其所附加的 SwiftUI 视图的坐标空间中的当前位置。

- **localTranslation**：表示手势识别器在其所附加的 SwiftUI 视图坐标空间中的当前平移量。

- **localVelocity**：表示手势识别器在其所附加的 SwiftUI 视图坐标空间中的当前速度。

## 实例方法

- **convert(globalPoint:to:)**：将全局坐标空间中的点转换为手势识别器所附加视图的祖先视图的 SwiftUI 坐标空间。

- **location(in:)**：将表示手势识别器的当前位置转换为手势识别器所附加视图的祖先视图的 SwiftUI 坐标空间。

- **translation(in:)**：将表示手势识别器的当前平移量转换为手势识别器所附加视图的祖先视图的 SwiftUI 坐标空间。

- **velocity(in:)**：将所表示的手势识别器的当前速度转换为其所附加视图的祖先视图的 SwiftUI 坐标空间。

## 将 UIKit 手势识别器添加到 SwiftUI 视图层级结构中

- **UIGestureRecognizerRepresentable**：`UIGestureRecognizer` 的包装器，用于将该手势识别器集成到您的 SwiftUI 层级结构中。

- **UIGestureRecognizerRepresentableContext**：用于创建和更新所表示的手势识别器的系统状态上下文信息。


---
source: https://developer.apple.com/documentation/SwiftUI/UIGestureRecognizerRepresentableCoordinateSpaceConverter
crawled: 2025-12-02T17:44:58Z
---

# UIGestureRecognizerRepresentableCoordinateSpaceConverter

**Structure**

A proxy structure used to convert locations to/from coordinate spaces in the hierarchy of the SwiftUI view associated with a [UIGestureRecognizerRepresentable](UIGestureRecognizerRepresentable.zh-Hans.md).

## Declaration

```swift
struct UIGestureRecognizerRepresentableCoordinateSpaceConverter
```

## Instance Properties

- **localLocation**: The represented gesture recognizer’s current location in the coordinate space of the SwiftUI view it’s attached to.
- **localTranslation**: The represented gesture recognizer’s current translation in the coordinate space of the SwiftUI view it’s attached to.
- **localVelocity**: The represented gesture recognizer’s current velocity in the coordinate space of the SwiftUI view it’s attached to.

## Instance Methods

- **convert(globalPoint:to:)**: Converts a point in the global coordinate space to a SwiftUI coordinate space of an ancestor of the view the gesture recognizer is attached to.
- **location(in:)**: Converts the represented gesture recognizer’s current location to a SwiftUI coordinate space  of an ancestor of the view the gesture recognizer is attached to.
- **translation(in:)**: Converts the represented gesture recognizer’s current translation to a SwiftUI coordinate space of an ancestor of the view the gesture recognizer is attached to.
- **velocity(in:)**: Converts the represented gesture recognizer’s current velocity to a SwiftUI coordinate space of an ancestor of the view the gesture recognizer is attached to.

## Adding UIKit gesture recognizers into SwiftUI view hierarchies

- **UIGestureRecognizerRepresentable**: A wrapper for a `UIGestureRecognizer` that you use to integrate that gesture recognizer into your SwiftUI hierarchy.
- **UIGestureRecognizerRepresentableContext**: Contextual information about the state of the system that you use to create and update a represented gesture recognizer.

