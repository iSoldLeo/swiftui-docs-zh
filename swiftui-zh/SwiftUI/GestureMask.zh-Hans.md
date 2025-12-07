--- 来源：https://developer.apple.com/documentation/SwiftUI/GestureMask

抓取时间：2025-12-02T17:41:03Z

---

# GestureMask

**Structure**

用于控制向视图添加手势如何影响该视图及其子视图识别的其他手势的选项。

## 声明

```swift
@frozen struct GestureMask
```

## 获取手势选项

- **all**：启用添加的手势以及视图及其子视图上的所有其他手势。

- **gesture**：启用添加的手势，但禁用子视图层级结构中的所有手势。

- **subviews**：启用子视图层级结构中的所有手势，但禁用添加的手势。

- **none**：禁用子视图层级结构中的所有手势，包括已添加的手势。

## 识别随时间变化的手势

- **gesture(_:)**：将 [NSGestureRecognizerRepresentable](NSGestureRecognizerRepresentable.zh-Hans.md) 附加到视图。

- **gesture(_:isEnabled:)**：将一个优先级低于视图自身定义的手势的手势附加到视图。

- **gesture(_:name:isEnabled:)**：将一个优先级低于视图自身定义的手势的手势附加到视图。

- **gesture(_:including:)**：将一个优先级低于视图自身定义的手势的手势附加到视图。

- **DragGesture**：拖动动作，当拖动事件序列发生变化时，会触发相应的操作。

- **WindowDragGesture**：一种识别并处理窗口拖动的手势。

- **MagnifyGesture**：一种识别并跟踪放大倍数的手势。

- **RotateGesture**：一种识别并跟踪旋转角度的手势。

- **RotateGesture3D**：一种识别并跟踪 3D 旋转角度和旋转轴的手势。

## 符合以下规范

- BitwiseCopyable

- Copyable

- Equatable

- ExpressibleByArrayLiteral

- OptionSet

- RawRepresentable

- Sendable

- SendableMetatype

- SetAlgebra


---
source: https://developer.apple.com/documentation/SwiftUI/GestureMask
crawled: 2025-12-02T17:41:03Z
---

# GestureMask

**Structure**

Options that control how adding a gesture to a view affects other gestures recognized by the view and its subviews.

## Declaration

```swift
@frozen struct GestureMask
```

## Getting gesture options

- **all**: Enable both the added gesture as well as all other gestures on the view and its subviews.
- **gesture**: Enable the added gesture but disable all gestures in the subview hierarchy.
- **subviews**: Enable all gestures in the subview hierarchy but disable the added gesture.
- **none**: Disable all gestures in the subview hierarchy, including the added gesture.

## Recognizing gestures that change over time

- **gesture(_:)**: Attaches an [NSGestureRecognizerRepresentable](NSGestureRecognizerRepresentable.zh-Hans.md) to the view.
- **gesture(_:isEnabled:)**: Attaches a gesture to the view with a lower precedence than gestures defined by the view.
- **gesture(_:name:isEnabled:)**: Attaches a gesture to the view with a lower precedence than gestures defined by the view.
- **gesture(_:including:)**: Attaches a gesture to the view with a lower precedence than gestures defined by the view.
- **DragGesture**: A dragging motion that invokes an action as the drag-event sequence changes.
- **WindowDragGesture**: A gesture that recognizes the motion of and handles dragging a window.
- **MagnifyGesture**: A gesture that recognizes a magnification motion and tracks the amount of magnification.
- **RotateGesture**: A gesture that recognizes a rotation motion and tracks the angle of the rotation.
- **RotateGesture3D**: A gesture that recognizes 3D rotation motion and tracks the angle and axis of the rotation.

## Conforms To

- BitwiseCopyable
- Copyable
- Equatable
- ExpressibleByArrayLiteral
- OptionSet
- RawRepresentable
- Sendable
- SendableMetatype
- SetAlgebra

