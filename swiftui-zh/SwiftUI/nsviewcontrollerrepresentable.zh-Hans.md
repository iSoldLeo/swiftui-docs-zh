---
来源： https://developer.apple.com/documentation/swiftui/nsviewcontrollerrepresentable
抓取时间： 2025-12-04T11:33:28Z
---

# NSViewControllerRepresentable

**Protocol**

封装器，用于将 AppKit 视图控制器集成到 SwiftUI 界面中。

## 声明

```swift
@MainActor @preconcurrency protocol NSViewControllerRepresentable : View where Self.Body == Never
```

## 概览

使用[NSViewControllerRepresentable](NSViewControllerRepresentable.zh-Hans.md) 实例来创建和管理 SwiftUI 界面中的[doc://com.apple.documentation/documentation/AppKit/NSViewController] 对象。在您应用程序的一个自定义实例中采用此协议，并使用其方法来创建、更新和删除视图控制器。创建和更新过程与 SwiftUI 视图的行为类似，您可以使用它们来根据应用程序的当前状态信息配置视图控制器。使用拆卸流程可以从 SwiftUI 中干净利落地删除视图控制器。例如，您可以使用拆卸流程通知其他对象视图控制器即将消失。

要将视图控制器添加到 SwiftUI 界面中，请创建`NSViewControllerRepresentable` 实例并将其添加到 SwiftUI 界面中。系统会在适当的时候调用自定义实例的方法。

系统不会自动将视图控制器中发生的更改传达给 SwiftUI 界面的其他部分。当您希望视图控制器与其他 SwiftUI 视图协调时，您必须提供一个 [Coordinator](NSViewControllerRepresentable/Coordinator.zh-Hans.md) 实例来促进这些交互。例如，您可以使用协调器将视图控制器中的 target-action 和委托消息转发给任何 SwiftUI 视图。



## 创建和更新视图控制器

- **makeNSViewController(context:)**：创建视图控制器对象并配置其初始状态。
- **updateNSViewController(_:context:)**：使用来自 SwiftUI 的新信息更新指定视图控制器的状态。
- **NSViewControllerRepresentable.Context**：使用来自 SwiftUI 的新信息更新指定视图控制器的状态。
- **NSViewControllerType**：要显示的视图控制器类型。

## 指定大小

- **sizeThatFits(_:nsViewController:context:)**：给定一个建议尺寸，返回复合视图的首选尺寸。

## 清理视图控制器

- **dismantleNSViewController(_:coordinator:)**：清理已提交的视图控制器（和协调器），以备移除。

## 提供自定义协调器对象

- **makeCoordinator()**：创建自定义对象，用于将视图控制器中的更改传达给 SwiftUI 界面的其他部分。
- **Coordinator**：用于与视图控制器协调的类型。

## 执行布局

- **NSViewControllerRepresentable.LayoutOptions**：与视图控制器协调的类型。

## 将 AppKit 视图添加到 SwiftUI 视图层次结构中

- **NSViewRepresentable**：封装器，用于将 AppKit 视图集成到 SwiftUI 视图层次结构中。
- **NSViewRepresentableContext**：有关系统状态的上下文信息，用于创建和更新 AppKit 视图。
- **NSViewControllerRepresentableContext**：您用来创建和更新 AppKit 视图控制器的系统状态的上下文信息。

## 继承自

- 视图


---
source: https://developer.apple.com/documentation/swiftui/nsviewcontrollerrepresentable
crawled: 2025-12-04T11:33:28Z
---

# NSViewControllerRepresentable

**Protocol**

A wrapper that you use to integrate an AppKit view controller into your SwiftUI interface.

## Declaration

```swift
@MainActor @preconcurrency protocol NSViewControllerRepresentable : View where Self.Body == Never
```

## Overview

Use an [NSViewControllerRepresentable](NSViewControllerRepresentable.zh-Hans.md) instance to create and manage an [doc://com.apple.documentation/documentation/AppKit/NSViewController] object in your SwiftUI interface. Adopt this protocol in one of your app’s custom instances, and use its methods to create, update, and tear down your view controller. The creation and update processes parallel the behavior of SwiftUI views, and you use them to configure your view controller with your app’s current state information. Use the teardown process to remove your view controller cleanly from your SwiftUI. For example, you might use the teardown process to notify other objects that the view controller is disappearing.

To add your view controller into your SwiftUI interface, create your `NSViewControllerRepresentable` instance and add it to your SwiftUI interface. The system calls the methods of your custom instance at appropriate times.

The system doesn’t automatically communicate changes occurring within your view controller to other parts of your SwiftUI interface. When you want your view controller to coordinate with other SwiftUI views, you must provide a [Coordinator](NSViewControllerRepresentable/Coordinator.zh-Hans.md) instance to facilitate those interactions. For example, you use a coordinator to forward target-action and delegate messages from your view controller to any SwiftUI views.



## Creating and updating the view controller

- **makeNSViewController(context:)**: Creates the view controller object and configures its initial state.
- **updateNSViewController(_:context:)**: Updates the state of the specified view controller with new information from SwiftUI.
- **NSViewControllerRepresentable.Context**
- **NSViewControllerType**: The type of view controller to present.

## Specifying a size

- **sizeThatFits(_:nsViewController:context:)**: Given a proposed size, returns the preferred size of the composite view.

## Cleaning up the view controller

- **dismantleNSViewController(_:coordinator:)**: Cleans up the presented view controller (and coordinator) in anticipation of its removal.

## Providing a custom coordinator object

- **makeCoordinator()**: Creates the custom object that you use to communicate changes from your view controller to other parts of your SwiftUI interface.
- **Coordinator**: A type to coordinate with the view controller.

## Performing layout

- **NSViewControllerRepresentable.LayoutOptions**

## Adding AppKit views to SwiftUI view hierarchies

- **NSViewRepresentable**: A wrapper that you use to integrate an AppKit view into your SwiftUI view hierarchy.
- **NSViewRepresentableContext**: Contextual information about the state of the system that you use to create and update your AppKit view.
- **NSViewControllerRepresentableContext**: Contextual information about the state of the system that you use to create and update your AppKit view controller.

## Inherits From

- View

