--- 来源：https://developer.apple.com/documentation/SwiftUI/NSGestureRecognizerRepresentable
抓取时间：2025-12-02T17:44:47Z

---

# NSGestureRecognizerRepresentable

**Protocol**

一个用于封装 `NSGestureRecognizer` 的包装器，用于将手势识别器集成到您的 SwiftUI 层级结构中。

## 声明

```swift
@MainActor @preconcurrency protocol NSGestureRecognizerRepresentable
```

## 概述

使用 [NSGestureRecognizerRepresentable](NSGestureRecognizerRepresentable.zh-Hans.md) 实例在您的 SwiftUI 界面中创建和管理 [doc://com.apple.documentation/documentation/AppKit/NSGestureRecognizer] 对象。

要将手势识别器添加到 SwiftUI 视图，请创建一个 [NSGestureRecognizerRepresentable](NSGestureRecognizerRepresentable.zh-Hans.md) 实例，并使用 [gesture(_:)](View/gesture.zh-Hans.md) 修饰符将其附加。系统会在适当的时候调用可表示实例的方法来创建和更新手势识别器。

以下示例展示了如何在视图层次结构中包含自定义的 `MyGestureRecognizer` 结构。

```swift
struct ContentView: View {
   var body: some View {
      VStack {
         Image("Mountain")
             .gesture(MyGestureRecognizer())
      }
   }
}
```

[NSGestureRecognizerRepresentable](NSGestureRecognizerRepresentable.zh-Hans.md) 类型可以使用环境并具有数据依赖关系，类似于视图和视图可表示对象。系统会调用实例上的相应方法来传播最新数据。

## 处理手势识别器操作

SwiftUI 会自动安装一个目标来代表您处理手势识别器的操作。实现 `handleNSGestureRecognizerAction` 方法来响应手势识别操作。

您可以选择包含一个协调器对象，用于转发来自手势识别器的委托消息或添加其他目标。

## 坐标空间转换

您创建的手势识别器可能未附加到层级结构中的 `NSView`，或者它返回的视图可能与您的 SwiftUI 视图的几何形状不同。

要处理这种情况，请使用上下文上的转换器执行从全局坐标空间到 SwiftUI 坐标空间的转换。您可以将手势识别器和 SwiftUI 坐标空间传递给转换器以检索最终转换后的点。传递 [local](CoordinateSpaceProtocol/local.zh-Hans.md) 坐标空间（默认值）将提供手势识别器附加到的 SwiftUI 视图中的点。

## 关联类型

- **Coordinator**：用于与手势识别器协调的类型。

- **NSGestureRecognizerType**：要呈现的 `NSGestureRecognizer` 的类型。

## 实例方法

- **handleNSGestureRecognizerAction(_:context:)**：处理所代表的 `NSGestureRecognizer` 的识别。

- **makeCoordinator(converter:)**：创建自定义对象，用于将手势识别器的状态更改传递给 SwiftUI 界面的其他部分。

- **makeNSGestureRecognizer(context:)**：创建所代表的手势识别器的实例。

- **updateNSGestureRecognizer(_:context:)**：将 `NSGestureRecognizer`（及其协调器）更新到最新配置。

## 类型别名

- **NSGestureRecognizerRepresentable.Context**：用于创建和更新手势识别器的系统状态上下文信息。

- **NSGestureRecognizerRepresentable.CoordinateSpaceConverter**：一种用于在关联的 SwiftUI 视图层级结构中转换坐标的类型。

## 将 AppKit 手势识别器添加到 SwiftUI 视图层级结构中

- **NSGestureRecognizerRepresentableContext**：用于创建和更新已表示的手势识别器的系统状态上下文信息。

- **NSGestureRecognizerRepresentableCoordinateSpaceConverter**：一种用于在与 [NSGestureRecognizerRepresentable](NSGestureRecognizerRepresentable.zh-Hans.md) 关联的 SwiftUI 视图层级结构中转换位置的结构。


---
source: https://developer.apple.com/documentation/SwiftUI/NSGestureRecognizerRepresentable
crawled: 2025-12-02T17:44:47Z
---

# NSGestureRecognizerRepresentable

**Protocol**

A wrapper for an `NSGestureRecognizer` that you use to integrate that gesture recognizer into your SwiftUI hierarchy.

## Declaration

```swift
@MainActor @preconcurrency protocol NSGestureRecognizerRepresentable
```

## Overview

Use an [NSGestureRecognizerRepresentable](NSGestureRecognizerRepresentable.zh-Hans.md) instance to create and manage an [doc://com.apple.documentation/documentation/AppKit/NSGestureRecognizer] object in your SwiftUI interface.

To add your gesture recognizer to a SwiftUI view, create an instance of [NSGestureRecognizerRepresentable](NSGestureRecognizerRepresentable.zh-Hans.md) and use the [gesture(_:)](View/gesture.zh-Hans.md) modifier to attach it. The system calls the methods of your representable instance at appropriate times to create and update the gesture recognizer.

The following example shows the inclusion of a custom `MyGestureRecognizer` structure in the view hierarchy.

```swift
struct ContentView: View {
   var body: some View {
      VStack {
         Image("Mountain")
             .gesture(MyGestureRecognizer())
      }
   }
}
```

[NSGestureRecognizerRepresentable](NSGestureRecognizerRepresentable.zh-Hans.md) types can use the environment and have data dependencies, similar to views and view representables. The system will call the appropriate methods on your instance to propagate the latest data.

## Handling Gesture Recognizer Actions

SwiftUI automatically installs a target to handle the gesture recognizer’s action on your behalf. Implement the `handleNSGestureRecognizerAction` method to react to the gesture recognizing its action.

You can optionally include a coordinator object to forward delegate messages from your gesture recognizer or add additional targets.

## Coordinate Space Conversions

The gesture recognizer you create may not be attached to an `NSView` in the hierarchy, or it may return a view with different geometry than your SwiftUI view.

To handle this, use the converter on the context to perform coordinate space conversions from the global coordinate space. You can pass the gesture recognizer and a SwiftUI coordinate space to the converter to retrieve a final converted point. Passing the [local](CoordinateSpaceProtocol/local.zh-Hans.md) coordinate space (the default) will provide the point in the SwiftUI view the gesture recognizer is attached to.

## Associated Types

- **Coordinator**: A type to coordinate with the gesture recognizer.
- **NSGestureRecognizerType**: The type of `NSGestureRecognizer` to be presented.

## Instance Methods

- **handleNSGestureRecognizerAction(_:context:)**: Handles recognition of the represented `NSGestureRecognizer`.
- **makeCoordinator(converter:)**: Creates the custom object that you use to communicate state changes from your gesture recognizer to other parts of your SwiftUI interface.
- **makeNSGestureRecognizer(context:)**: Creates an instance of the represented gesture recognizer.
- **updateNSGestureRecognizer(_:context:)**: Updates the `NSGestureRecognizer` (and coordinator) to the latest configuration.

## Type Aliases

- **NSGestureRecognizerRepresentable.Context**: Contextual information about the state of the system that you use to create and update your gesture recognizer.
- **NSGestureRecognizerRepresentable.CoordinateSpaceConverter**: A type used to convert coordinates to/from coordinate spaces in the hierarchy of the associated SwiftUI view.

## Adding AppKit gesture recognizers into SwiftUI view hierarchies

- **NSGestureRecognizerRepresentableContext**: Contextual information about the state of the system that you use to create and update a represented gesture recognizer.
- **NSGestureRecognizerRepresentableCoordinateSpaceConverter**: A structure used to convert locations to and from coordinate spaces in the hierarchy of the SwiftUI view associated with an [NSGestureRecognizerRepresentable](NSGestureRecognizerRepresentable.zh-Hans.md).

