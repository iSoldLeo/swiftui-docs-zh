---
来源： https://developer.apple.com/documentation/SwiftUI/UIGestureRecognizerRepresentable
抓取时间： 2025-12-02T17:44:56Z
---

# UIGestureRecognizerRepresentable

**Protocol**

用于将手势识别器集成到 SwiftUI 层次结构中的`UIGestureRecognizer` 的包装器。

## 声明

```swift
@MainActor @preconcurrency protocol UIGestureRecognizerRepresentable
```

## 概览

使用 [UIGestureRecognizerRepresentable](UIGestureRecognizerRepresentable.zh-Hans.md) 实例来创建和管理 SwiftUI 界面中的[doc://com.apple.documentation/documentation/UIKit/UIGestureRecognizer] 对象。

要将手势识别器添加到 SwiftUI 视图中，请创建一个 [UIGestureRecognizerRepresentable](UIGestureRecognizerRepresentable.zh-Hans.md) 实例，并使用 [gesture(_:)](View/gesture.zh-Hans.md) 修改器来附加它。系统会在适当的时候调用可表示实例的方法来创建和更新手势识别器。

下面的示例显示了在视图层次结构中加入自定义`MyGestureRecognizer`结构的情况。

```swift
struct ContentView: View {
   var body: some View {
      VStack {
         Image("Mountain").gesture(MyGestureRecognizer())
      }
   }
}
```

由于[UIGestureRecognizerRepresentable](UIGestureRecognizerRepresentable.zh-Hans.md) 是一个结构体，因此它可以使用环境、具有数据依赖性，并且与 SwiftUI 中的视图更为相似。系统将在您的实例上调用相应的方法来传播最新数据。

## 处理手势识别器操作

SwiftUI 会自动安装一个目标，以代表您处理手势识别器的操作。执行`handleUIGestureRecognizerAction`方法，对手势识别器的动作做出反应。

您可以选择包含一个协调器对象，以转发来自手势识别器的委托消息或添加其他目标。

## 坐标空间转换

您创建的手势识别器可能没有连接到层次结构中的`UIView`，或者它返回的视图可能与您的 SwiftUI 视图的几何形状不同。

要处理这种情况，可以使用上下文中的转换器从全局坐标空间执行坐标空间转换。您可以将手势识别器和 SwiftUI 坐标空间传递给转换器，以获取最终转换后的点。传递[local](CoordinateSpaceProtocol/local.zh-Hans.md)坐标空间（默认值）将提供手势识别器所连接的 SwiftUI 视图中的点。

### 相关类型

- **Coordinator**：与手势识别器协调的类型。
- **UIGestureRecognizerType**：要显示的`UIGestureRecognizer` 类型。

### 实例方法

- **handleUIGestureRecognizerAction(_:context:)**：处理识别所代表的`UIGestureRecognizer`。
- **makeCoordinator(converter:)**：创建自定义对象，用于将状态变化从手势识别器传递到 SwiftUI 界面的其他部分。
- **makeUIGestureRecognizer(context:)**：创建所代表手势识别器的实例。
- **updateUIGestureRecognizer(_:context:)**：将`UIGestureRecognizer`（和协调器）更新为最新配置。

## 类型别名

- **UIGestureRecognizerRepresentable.Context**：有关系统状态的上下文信息，用于创建和更新手势识别器。
- **UIGestureRecognizerRepresentable.CoordinateSpaceConverter**：用于在相关 SwiftUI 视图的层次结构中将坐标转换为/从坐标空间转换为坐标的类型。

## 在 SwiftUI 视图层次结构中添加 UIKit 手势识别器

- **UIGestureRecognizerRepresentableContext**：有关系统状态的上下文信息，用于创建和更新所代表的手势识别器。
- **UIGestureRecognizerRepresentableCoordinateSpaceConverter**：代理结构，用于将位置转换为与 [UIGestureRecognizerRepresentable](UIGestureRecognizerRepresentable.zh-Hans.md)相关联的 SwiftUI 视图层次结构中的坐标空间/从坐标空间转换为位置。


---
source: https://developer.apple.com/documentation/SwiftUI/UIGestureRecognizerRepresentable
crawled: 2025-12-02T17:44:56Z
---

# UIGestureRecognizerRepresentable

**Protocol**

A wrapper for a `UIGestureRecognizer` that you use to integrate that gesture recognizer into your SwiftUI hierarchy.

## Declaration

```swift
@MainActor @preconcurrency protocol UIGestureRecognizerRepresentable
```

## Overview

Use a [UIGestureRecognizerRepresentable](UIGestureRecognizerRepresentable.zh-Hans.md) instance to create and manage a [doc://com.apple.documentation/documentation/UIKit/UIGestureRecognizer] object in your SwiftUI interface.

To add your gesture recognizer to a SwiftUI view, create an instance of [UIGestureRecognizerRepresentable](UIGestureRecognizerRepresentable.zh-Hans.md) and use the [gesture(_:)](View/gesture.zh-Hans.md) modifier to attach it. The system calls the methods of your representable instance at appropriate times to create and update the gesture recognizer.

The following example shows the inclusion of a custom `MyGestureRecognizer` structure in the view hierarchy.

```swift
struct ContentView: View {
   var body: some View {
      VStack {
         Image("Mountain").gesture(MyGestureRecognizer())
      }
   }
}
```

Because your [UIGestureRecognizerRepresentable](UIGestureRecognizerRepresentable.zh-Hans.md) is a struct, it can use the environment, have data dependencies, and is more similar to views in SwiftUI. The system will call the appropriate methods on your instance to propagate the latest data.

## Handling Gesture Recognizer Actions

SwiftUI automatically installs a target to handle the gesture recognizer’s action on your behalf. Implement the `handleUIGestureRecognizerAction` method to react to the gesture recognizing its action.

You can optionally include a coordinator object to forward delegate messages from your gesture recognizer or add additional targets.

## Coordinate Space Conversions

The gesture recognizer you create may not be attached to a `UIView` in the hierarchy, or it may return a view with different geometry than your SwiftUI view.

To handle this, use the converter on the context to perform coordinate space conversions from the global coordinate space. You can pass the gesture recognizer and a SwiftUI coordinate space to the converter to retrieve a final converted point. Passing the [local](CoordinateSpaceProtocol/local.zh-Hans.md) coordinate space (the default) will provide the point in the SwiftUI view the gesture recognizer is attached to.

## Associated Types

- **Coordinator**: A type to coordinate with the gesture recognizer.
- **UIGestureRecognizerType**: The type of `UIGestureRecognizer` to be presented.

## Instance Methods

- **handleUIGestureRecognizerAction(_:context:)**: Handles recognition of the represented `UIGestureRecognizer`.
- **makeCoordinator(converter:)**: Creates the custom object that you use to communicate state changes from your gesture recognizer to other parts of your SwiftUI interface.
- **makeUIGestureRecognizer(context:)**: Creates an instance of the represented gesture recognizer.
- **updateUIGestureRecognizer(_:context:)**: Updates the `UIGestureRecognizer` (and coordinator) to the latest configuration.

## Type Aliases

- **UIGestureRecognizerRepresentable.Context**: Contextual information about the state of the system that you use to create and update your gesture recognizer.
- **UIGestureRecognizerRepresentable.CoordinateSpaceConverter**: A type used to convert coordinates to/from coordinate spaces in the hierarchy of the associated SwiftUI view.

## Adding UIKit gesture recognizers into SwiftUI view hierarchies

- **UIGestureRecognizerRepresentableContext**: Contextual information about the state of the system that you use to create and update a represented gesture recognizer.
- **UIGestureRecognizerRepresentableCoordinateSpaceConverter**: A proxy structure used to convert locations to/from coordinate spaces in the hierarchy of the SwiftUI view associated with a [UIGestureRecognizerRepresentable](UIGestureRecognizerRepresentable.zh-Hans.md).

