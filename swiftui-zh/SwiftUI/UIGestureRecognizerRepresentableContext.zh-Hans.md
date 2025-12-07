---
来源： https://developer.apple.com/documentation/SwiftUI/UIGestureRecognizerRepresentableContext
抓取时间： 2025-12-02T17:44:57Z
---

# UIGestureRecognizerRepresentableContext

**Structure**

有关系统状态的上下文信息，用于创建和更新所代表的手势识别器。

## 声明

```swift
struct UIGestureRecognizerRepresentableContext<Representable> where Representable : UIGestureRecognizerRepresentable
```

## 实例属性

- **converter**：用于在相关 SwiftUI 视图的层次结构中将位置转换为/从坐标空间转换为坐标空间的结构。
- **coordinator**：自定义对象，用于将状态变化从手势识别器传递到 SwiftUI 界面的其他部分。

## 在 SwiftUI 视图层次中添加 UIKit 手势识别器

- **UIGestureRecognizerRepresentable**：用于将手势识别器集成到 SwiftUI 层次结构中的`UIGestureRecognizer` 包装器。
- **UIGestureRecognizerRepresentableCoordinateSpaceConverter**：代理结构，用于在与 [UIGestureRecognizerRepresentable](UIGestureRecognizerRepresentable.zh-Hans.md)相关联的 SwiftUI 视图层次结构中将位置转换为坐标空间或从坐标空间转换为位置。


---
source: https://developer.apple.com/documentation/SwiftUI/UIGestureRecognizerRepresentableContext
crawled: 2025-12-02T17:44:57Z
---

# UIGestureRecognizerRepresentableContext

**Structure**

Contextual information about the state of the system that you use to create and update a represented gesture recognizer.

## Declaration

```swift
struct UIGestureRecognizerRepresentableContext<Representable> where Representable : UIGestureRecognizerRepresentable
```

## Instance Properties

- **converter**: A structure used to convert locations to/from coordinate spaces in the hierarchy of the associated SwiftUI view.
- **coordinator**: The custom object that you use to communicate state changes from your gesture recognizer to other parts of your SwiftUI interface.

## Adding UIKit gesture recognizers into SwiftUI view hierarchies

- **UIGestureRecognizerRepresentable**: A wrapper for a `UIGestureRecognizer` that you use to integrate that gesture recognizer into your SwiftUI hierarchy.
- **UIGestureRecognizerRepresentableCoordinateSpaceConverter**: A proxy structure used to convert locations to/from coordinate spaces in the hierarchy of the SwiftUI view associated with a [UIGestureRecognizerRepresentable](UIGestureRecognizerRepresentable.zh-Hans.md).

