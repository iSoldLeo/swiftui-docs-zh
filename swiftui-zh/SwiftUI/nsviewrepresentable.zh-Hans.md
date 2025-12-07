--- 来源：https://developer.apple.com/documentation/swiftui/nsviewrepresentable
抓取时间：2025-12-04T11:33:33Z
---

# NSViewRepresentable

**Protocol**

一个用于将 AppKit 视图集成到 SwiftUI 视图层级结构中的包装器。

## 声明

```swift
@MainActor @preconcurrency protocol NSViewRepresentable : View where Self.Body == Never
```

## 概述

使用 `NSViewRepresentable` 实例在 SwiftUI 界面中创建和管理 [doc://com.apple.documentation/documentation/AppKit/NSView] 对象。在应用程序的自定义实例之一中采用此协议，并使用其方法来创建、更新和销毁视图。创建和更新过程与 SwiftUI 视图的行为类似，您可以使用它们来根据应用程序的当前状态信息配置视图。使用销毁过程可以从 SwiftUI 中干净地移除视图。例如，您可以使用清理过程来通知其他对象视图即将消失。

要将视图添加到 SwiftUI 界面，请创建 [NSViewRepresentable](NSViewRepresentable.zh-Hans.md) 实例并将其添加到 SwiftUI 界面。系统会在适当的时候调用可表示实例的方法来创建和更新视图。以下示例展示了如何在视图层次结构中包含自定义 `MyRepresentedCustomView` 结构。

```swift
struct ContentView: View {
   var body: some View {
      VStack {
         Text("Global Sales")
         MyRepresentedCustomView()
      }
   }
}
```

系统不会自动将视图控制器中发生的更改传递给 SwiftUI 界面的其他部分。如果您希望视图控制器与其他 SwiftUI 视图协调，则必须提供一个 [Coordinator](NSViewControllerRepresentable/Coordinator.zh-Hans.md) 对象来促进这些交互。例如，您可以使用协调器将来自视图控制器的目标操作和委托消息转发到任何 SwiftUI 视图。

## 创建和更新视图

- **makeNSView(context:)**：创建视图对象并配置其初始状态。

- **updateNSView(_:context:)**：使用来自 SwiftUI 的新信息更新指定视图的状态。

- **NSViewRepresentable.Context**

- **NSViewType**：要呈现的视图类型。

## 指定大小

- **sizeThatFits(_:nsView:context:)**：给定一个建议的大小，返回组合视图的首选大小。

## 清理视图

- **dismantleNSView(_:coordinator:)**：清理已呈现的 AppKit 视图（及其协调器），以便将其移除。

## 提供自定义协调器对象

- **makeCoordinator()**：创建自定义实例，用于将视图的更改传递给 SwiftUI 界面的其他部分。

- **Coordinator**：用于与视图协调的类型。

## 执行布局

- **NSViewRepresentable.LayoutOptions**

## 将 AppKit 视图添加到 SwiftUI 视图层级结构

- **NSViewRepresentableContext**：用于创建和更新 AppKit 视图的系统状态上下文信息。

- **NSViewControllerRepresentable**：用于将 AppKit 视图控制器集成到 SwiftUI 界面中的包装器。

- **NSViewControllerRepresentableContext**：用于创建和更新 AppKit 视图控制器的系统状态上下文信息。

## 继承自

- 查看


---
source: https://developer.apple.com/documentation/swiftui/nsviewrepresentable
crawled: 2025-12-04T11:33:33Z
---

# NSViewRepresentable

**Protocol**

A wrapper that you use to integrate an AppKit view into your SwiftUI view hierarchy.

## Declaration

```swift
@MainActor @preconcurrency protocol NSViewRepresentable : View where Self.Body == Never
```

## Overview

Use an `NSViewRepresentable` instance to create and manage an [doc://com.apple.documentation/documentation/AppKit/NSView] object in your SwiftUI interface. Adopt this protocol in one of your app’s custom instances, and use its methods to create, update, and tear down your view. The creation and update processes parallel the behavior of SwiftUI views, and you use them to configure your view with your app’s current state information. Use the teardown process to remove your view cleanly from your SwiftUI. For example, you might use the teardown process to notify other objects that the view is disappearing.

To add your view into your SwiftUI interface, create your [NSViewRepresentable](NSViewRepresentable.zh-Hans.md) instance and add it to your SwiftUI interface. The system calls the methods of your representable instance at appropriate times to create and update the view. The following example shows the inclusion of a custom `MyRepresentedCustomView` struct in the view hierarchy.

```swift
struct ContentView: View {
   var body: some View {
      VStack {
         Text("Global Sales")
         MyRepresentedCustomView()
      }
   }
}
```

The system doesn’t automatically communicate changes occurring within your view controller to other parts of your SwiftUI interface. When you want your view controller to coordinate with other SwiftUI views, you must provide a [Coordinator](NSViewControllerRepresentable/Coordinator.zh-Hans.md) object to facilitate those interactions. For example, you use a coordinator to forward target-action and delegate messages from your view controller to any SwiftUI views.



## Creating and updating the view

- **makeNSView(context:)**: Creates the view object and configures its initial state.
- **updateNSView(_:context:)**: Updates the state of the specified view with new information from SwiftUI.
- **NSViewRepresentable.Context**
- **NSViewType**: The type of view to present.

## Specifying a size

- **sizeThatFits(_:nsView:context:)**: Given a proposed size, returns the preferred size of the composite view.

## Cleaning up the view

- **dismantleNSView(_:coordinator:)**: Cleans up the presented AppKit view (and coordinator) in anticipation of their removal.

## Providing a custom coordinator object

- **makeCoordinator()**: Creates the custom instance that you use to communicate changes from your view to other parts of your SwiftUI interface.
- **Coordinator**: A type to coordinate with the view.

## Performing layout

- **NSViewRepresentable.LayoutOptions**

## Adding AppKit views to SwiftUI view hierarchies

- **NSViewRepresentableContext**: Contextual information about the state of the system that you use to create and update your AppKit view.
- **NSViewControllerRepresentable**: A wrapper that you use to integrate an AppKit view controller into your SwiftUI interface.
- **NSViewControllerRepresentableContext**: Contextual information about the state of the system that you use to create and update your AppKit view controller.

## Inherits From

- View

