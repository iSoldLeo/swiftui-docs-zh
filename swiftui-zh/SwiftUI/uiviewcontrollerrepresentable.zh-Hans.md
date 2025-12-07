--- 来源：https://developer.apple.com/documentation/swiftui/uiviewcontrollerrepresentable
抓取时间：2025-12-04T11:33:39Z

---

# UIViewControllerRepresentable

**Protocol**

一个代表 UIKit 视图控制器的视图。

## 声明

```swift
@MainActor @preconcurrency protocol UIViewControllerRepresentable : View where Self.Body == Never
```

## 概述

使用 [UIViewControllerRepresentable](UIViewControllerRepresentable.zh-Hans.md) 实例在 SwiftUI 界面中创建和管理 [doc://com.apple.documentation/documentation/UIKit/UIViewController] 对象。在应用的自定义实例中采用此协议，并使用其方法来创建、更新和销毁视图控制器。创建和更新过程与 SwiftUI 视图的行为类似，您可以使用它们来配置视图控制器，使其包含应用的当前状态信息。使用销毁过程可以从 SwiftUI 中干净地移除视图控制器。例如，您可以使用清理过程来通知其他对象视图控制器即将消失。

要将视图控制器添加到 SwiftUI 界面，请创建 [UIViewControllerRepresentable](UIViewControllerRepresentable.zh-Hans.md) 实例并将其添加到 SwiftUI 界面。系统会在适当的时候调用自定义实例的方法。

系统不会自动将视图控制器内部发生的更改传递给 SwiftUI 界面的其他部分。如果您希望视图控制器与其他 SwiftUI 视图协调，则必须提供一个 [Coordinator](NSViewControllerRepresentable/Coordinator.zh-Hans.md) 实例来促进这些交互。例如，您可以使用协调器将来自视图控制器的目标操作和委托消息转发到任何 SwiftUI 视图。

## 创建和更新视图控制器

- **makeUIViewController(context:)**：创建视图控制器对象并配置其初始状态。

- **updateUIViewController(_:context:)**：使用来自 SwiftUI 的新信息更新指定视图控制器的状态。

- **UIViewControllerRepresentable.Context**

- **UIViewControllerType**：要呈现的视图控制器类型。

## 指定大小

- **sizeThatFits(_:uiViewController:context:)**：给定一个建议的大小，返回组合视图的首选大小。

## 清理视图控制器

- **dismantleUIViewController(_:coordinator:)**：清理已呈现的视图控制器（及其协调器），以便将其移除。

## 提供自定义协调器对象

- **makeCoordinator()**：创建自定义实例，用于将视图控制器中的更改传递给 SwiftUI 界面的其他部分。

- **Coordinator**：用于与视图控制器协调的类型。

## 执行布局

- **UIViewControllerRepresentable.LayoutOptions**

## 将 UIKit 视图添加到 SwiftUI 视图层级结构

- **UIViewRepresentable**：用于将 UIKit 视图集成到 SwiftUI 视图层级结构中的包装器。

- **UIViewRepresentableContext**：用于创建和更新 UIKit 视图的系统状态上下文信息。

- **UIViewControllerRepresentableContext**：用于创建和更新 UIKit 视图控制器的系统状态上下文信息。

## 继承自

- View


---
source: https://developer.apple.com/documentation/swiftui/uiviewcontrollerrepresentable
crawled: 2025-12-04T11:33:39Z
---

# UIViewControllerRepresentable

**Protocol**

A view that represents a UIKit view controller.

## Declaration

```swift
@MainActor @preconcurrency protocol UIViewControllerRepresentable : View where Self.Body == Never
```

## Overview

Use a [UIViewControllerRepresentable](UIViewControllerRepresentable.zh-Hans.md) instance to create and manage a [doc://com.apple.documentation/documentation/UIKit/UIViewController] object in your SwiftUI interface. Adopt this protocol in one of your app’s custom instances, and use its methods to create, update, and tear down your view controller. The creation and update processes parallel the behavior of SwiftUI views, and you use them to configure your view controller with your app’s current state information. Use the teardown process to remove your view controller cleanly from your SwiftUI. For example, you might use the teardown process to notify other objects that the view controller is disappearing.

To add your view controller into your SwiftUI interface, create your [UIViewControllerRepresentable](UIViewControllerRepresentable.zh-Hans.md) instance and add it to your SwiftUI interface. The system calls the methods of your custom instance at appropriate times.

The system doesn’t automatically communicate changes occurring within your view controller to other parts of your SwiftUI interface. When you want your view controller to coordinate with other SwiftUI views, you must provide a [Coordinator](NSViewControllerRepresentable/Coordinator.zh-Hans.md) instance to facilitate those interactions. For example, you use a coordinator to forward target-action and delegate messages from your view controller to any SwiftUI views.



## Creating and updating the view controller

- **makeUIViewController(context:)**: Creates the view controller object and configures its initial state.
- **updateUIViewController(_:context:)**: Updates the state of the specified view controller with new information from SwiftUI.
- **UIViewControllerRepresentable.Context**
- **UIViewControllerType**: The type of view controller to present.

## Specifying a size

- **sizeThatFits(_:uiViewController:context:)**: Given a proposed size, returns the preferred size of the composite view.

## Cleaning up the view controller

- **dismantleUIViewController(_:coordinator:)**: Cleans up the presented view controller (and coordinator) in anticipation of their removal.

## Providing a custom coordinator object

- **makeCoordinator()**: Creates the custom instance that you use to communicate changes from your view controller to other parts of your SwiftUI interface.
- **Coordinator**: A type to coordinate with the view controller.

## Performing layout

- **UIViewControllerRepresentable.LayoutOptions**

## Adding UIKit views to SwiftUI view hierarchies

- **UIViewRepresentable**: A wrapper for a UIKit view that you use to integrate that view into your SwiftUI view hierarchy.
- **UIViewRepresentableContext**: Contextual information about the state of the system that you use to create and update your UIKit view.
- **UIViewControllerRepresentableContext**: Contextual information about the state of the system that you use to create and update your UIKit view controller.

## Inherits From

- View

