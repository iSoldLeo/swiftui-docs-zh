---
来源： https://developer.apple.com/documentation/SwiftUI/Unifying-your-app-s-animations
抓取时间： 2025-12-02T17:44:40Z
---

# 统一应用程序的动画

**Article**

在 SwiftUI、UIKit 和 AppKit 中创建一致的 UI 动画体验。

## 概览

许多应用程序结合使用 SwiftUI、UIKit 和 AppKit 来构建界面并制作动画。在 iOS 18 及更高版本中，您可以在 UIKit 和 AppKit 中使用 SwiftUI 动画。SwiftUI 提供了多种标准和自定义动画类型。



SwiftUI、UIKit 和 AppKit 使用不同的动画底层实现。使用多个框架制作动画的应用程序可能会遇到某些问题，例如动画时序同步或其他不一致问题，这些问题可能难以排除，并导致用户体验不理想。使用 SwiftUI 动画可以在所有这些框架中为 UI 制作动画，从而在每个平台上创建更加一致和无缝的体验。

### 创建 SwiftUI 动画

要在 UIKit 或 AppKit 中创建 SwiftUI 动画，请导入 SwiftUI 并创建一个 SwiftUI [Animation](Animation.zh-Hans.md)。然后，将该动画作为参数传递给 `UIView` 上的[doc://com.apple.documentation/documentation/UIKit/UIView/animate(_:changes:completion:)] 类方法，或 `NSAnimationContext` 上的[doc://com.apple.documentation/documentation/AppKit/NSAnimationContext/animate(_:changes:completion:)] 类方法。下面的示例比较了如何在 SwiftUI、UIKit 和 AppKit 中使用 SwiftUI [Animation](Animation.zh-Hans.md) 类型创建基本的弹簧动画。



### 使用 SwiftUI 动画的完成处理程序

您可以为这些动画方法提供一个可选的完成处理程序，系统会在动画完成后自动调用该处理程序。下面的示例展示了一个完成处理程序，它可以在动画完成时更改视图的背景颜色。



### 重定向 SwiftUI 动画

与 SwiftUI 视图中的动画类似，您可以使用`UIView` 上的[doc://com.apple.documentation/documentation/UIKit/UIView/animate(_:changes:completion:)] 类方法或`NSAnimationContext` 上的[doc://com.apple.documentation/documentation/AppKit/NSAnimationContext/animate(_:changes:completion:)] 类方法平滑地重定目标动画。重定向 SwiftUI 动画会使用之前动画的速度，以连续的速度向前推进动画，从而创建流畅的动画体验。以下示例展示了重定向正在进行的动画。



### 解决动画问题

跨框架同步动画可能会在不同的实现中出现不同的行为。在排除应用程序中的动画故障时，请牢记以下提示：

- SwiftUI 动画在应用程序进程的后台线程上运行。
- SwiftUI 动画没有后置[doc://com.apple.documentation/documentation/QuartzCore/CAAnimation]，这一点使其有别于[doc://com.apple.documentation/documentation/UIKit/UIView]动画。
- SwiftUI 动画与 [doc://com.apple.documentation/documentation/UIKit/UIViewPropertyAnimator] 或 `UIView` 关键帧动画不兼容。

有关在应用程序中提供出色动画体验的更多信息，请参阅 [https://developer.apple.com/wwdc24/10145/]。

### 相关文档

- **Animation**：视图随时间变化的方式，用于创建从一种状态到另一种状态的平滑视觉过渡。
- **withAnimation(_:_:)**：返回使用所提供的动画重新计算视图主体的结果。
- **animate(_:changes:completion:)**：返回视图主体与所提供动画重新计算的结果。
- **animate(_:changes:completion:)**：使用指定的 SwiftUI 动画为一个或多个视图的变化制作动画。

## 在 AppKit 中显示 SwiftUI 视图

- **NSHostingController**：承载 SwiftUI 视图层次结构的 AppKit 视图控制器。
- **NSHostingView**：托管 SwiftUI 视图层次结构的 AppKit 视图。
- **NSHostingMenu**：包含由 SwiftUI 视图定义的菜单项的 AppKit 菜单。
- **NSHostingSizingOptions**：关于托管视图和控制器如何将其内容的大小反映到自动布局约束中的选项。
- **NSHostingSceneRepresentation**：承载并可呈现 SwiftUI 场景的 AppKit 类型
- **NSHostingSceneBridgingOptions**：托管视图和控制器如何管理相关窗口的选项。


---
source: https://developer.apple.com/documentation/SwiftUI/Unifying-your-app-s-animations
crawled: 2025-12-02T17:44:40Z
---

# Unifying your app’s animations

**Article**

Create a consistent UI animation experience across SwiftUI, UIKit, and AppKit.

## Overview

Many apps use a combination of SwiftUI, UIKit, and AppKit to build and animate their interfaces. In iOS 18 and later, you can use SwiftUI animations in UIKit and AppKit. SwiftUI provides a wide range of standard as well as custom animation types.



SwiftUI, UIKit, and AppKit use different underlying implementations for animation. Apps that use multiple frameworks for animation might encounter certain issues, such as syncing animation timing or other inconsistencies, that can be difficult to troubleshoot and lead to a suboptimal user experience. Use SwiftUI animations to animate UI across all of these frameworks to create a more consistent and seamless experience on every platform.

### Create a SwiftUI animation

To create a SwiftUI animation in UIKit or AppKit, import SwiftUI and create a SwiftUI [Animation](Animation.zh-Hans.md). Then, pass that animation as a parameter into the [doc://com.apple.documentation/documentation/UIKit/UIView/animate(_:changes:completion:)] class method on `UIView`, or the [doc://com.apple.documentation/documentation/AppKit/NSAnimationContext/animate(_:changes:completion:)] class method on `NSAnimationContext`. The following examples compare how you can create a basic spring animation using a SwiftUI [Animation](Animation.zh-Hans.md) type across SwiftUI, UIKit, and AppKit.



### Use completion handlers with SwiftUI animations

You can provide an optional completion handler to these animation methods, which the system calls automatically after the animations complete. The following examples show a completion handler that changes the background color of the view to indicate when the animation completes.



### Retarget a SwiftUI animation

Similar to animations in SwiftUI views, you can smoothly retarget the animations you perform using the [doc://com.apple.documentation/documentation/UIKit/UIView/animate(_:changes:completion:)] class method on `UIView` or the [doc://com.apple.documentation/documentation/AppKit/NSAnimationContext/animate(_:changes:completion:)] class method on `NSAnimationContext`. Retargeting a SwiftUI animation uses the velocity from the previous animations to carry the animation forward with continuous velocity, creating a fluid animation experience. The following examples show retargeting an in-progress animation.



### Troubleshoot animations

Syncing animations across frameworks can surface differing behavior across implementations. Keep these tips in mind when you troubleshoot animations in your app:

- SwiftUI animations run on a background thread in your app’s process.
- SwiftUI animations don’t have a backing [doc://com.apple.documentation/documentation/QuartzCore/CAAnimation], which differentiates them from [doc://com.apple.documentation/documentation/UIKit/UIView] animations.
- SwiftUI animations aren’t compatible with [doc://com.apple.documentation/documentation/UIKit/UIViewPropertyAnimator] or `UIView` keyframe animations.

For more information about providing a great animation experience in your app, see [https://developer.apple.com/wwdc24/10145/].

## Related Documentation

- **Animation**: The way a view changes over time to create a smooth visual transition from one state to another.
- **withAnimation(_:_:)**: Returns the result of recomputing the view’s body with the provided animation.
- **animate(_:changes:completion:)**
- **animate(_:changes:completion:)**: Animate changes to one or more views using the specified SwiftUI animation.

## Displaying SwiftUI views in AppKit

- **NSHostingController**: An AppKit view controller that hosts SwiftUI view hierarchy.
- **NSHostingView**: An AppKit view that hosts a SwiftUI view hierarchy.
- **NSHostingMenu**: An AppKit menu with menu items that are defined by a SwiftUI View.
- **NSHostingSizingOptions**: Options for how hosting views and controllers reflect their content’s size into Auto Layout constraints.
- **NSHostingSceneRepresentation**: An AppKit type that hosts and can present SwiftUI scenes
- **NSHostingSceneBridgingOptions**: Options for how hosting views and controllers manage aspects of the associated window.

