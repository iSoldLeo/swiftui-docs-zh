---
来源： https://developer.apple.com/documentation/swiftui/uiviewrepresentable
抓取时间： 2025-12-04T11:33:42Z
---

# UIViewRepresentable

**Protocol**

UIKit 视图的封装器，用于将该视图集成到 SwiftUI 视图层次结构中。

## 声明

```swift
@MainActor @preconcurrency protocol UIViewRepresentable : View where Self.Body == Never
```

## 概览

在 SwiftUI 界面中使用[UIViewRepresentable](UIViewRepresentable.zh-Hans.md) 实例来创建和管理[doc://com.apple.documentation/documentation/UIKit/UIView] 对象。在您应用程序的自定义实例中采用该协议，并使用其方法来创建、更新和删除视图。创建和更新过程与 SwiftUI 视图的行为类似，您可以使用它们来根据应用程序的当前状态信息配置视图。使用拆卸流程可以从 SwiftUI 中干净利落地删除视图。例如，您可以使用拆卸流程通知其他对象视图即将消失。

要将视图添加到 SwiftUI 界面中，请创建您的[UIViewRepresentable](UIViewRepresentable.zh-Hans.md) 实例并将其添加到 SwiftUI 界面中。系统会在适当的时候调用您的可表示实例的方法来创建和更新视图。下面的示例显示了在视图层次结构中包含自定义`MyRepresentedCustomView` 结构的情况。

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

系统不会自动将视图中发生的更改传达给 SwiftUI 界面的其他部分。当您希望视图与其他 SwiftUI 视图协调时，您必须提供一个 [Coordinator](NSViewControllerRepresentable/Coordinator.zh-Hans.md) 实例来促进这些交互。例如，您可以使用协调器将您视图中的 target-action 和委托消息转发给任何 SwiftUI 视图。



## 创建和更新视图

- **makeUIView(context:)**：创建视图对象并配置其初始状态。
- **updateUIView(_:context:)**：使用来自 SwiftUI 的新信息更新指定视图的状态。
- **UIViewRepresentable.Context**：使用来自 SwiftUI 的新信息更新指定视图的状态。
- **UIViewType**：要显示的视图类型。

## 指定大小

- **sizeThatFits(_:uiView:context:)**：给定一个建议尺寸，返回首选的复合视图尺寸。

## 清理视图

- **dismantleUIView(_:coordinator:)**：清理显示的 UIKit 视图（和协调器），以备移除。

## 提供自定义协调器对象

- **makeCoordinator()**：创建自定义实例，用于将视图中的更改传达给 SwiftUI 界面的其他部分。
- **Coordinator**：与视图协调的类型。

## 执行布局

- **UIViewRepresentable.LayoutOptions**：与视图协调的类型。

## 将 UIKit 视图添加到 SwiftUI 视图层次中

- **UIViewRepresentableContext**：有关系统状态的上下文信息，用于创建和更新 UIKit 视图。
- **UIViewControllerRepresentable**：表示 UIKit 视图控制器的视图。
- **UIViewControllerRepresentableContext**：有关系统状态的上下文信息，用于创建和更新 UIKit 视图控制器。

## 继承自

- 视图


---
source: https://developer.apple.com/documentation/swiftui/uiviewrepresentable
crawled: 2025-12-04T11:33:42Z
---

# UIViewRepresentable

**Protocol**

A wrapper for a UIKit view that you use to integrate that view into your SwiftUI view hierarchy.

## Declaration

```swift
@MainActor @preconcurrency protocol UIViewRepresentable : View where Self.Body == Never
```

## Overview

Use a [UIViewRepresentable](UIViewRepresentable.zh-Hans.md) instance to create and manage a [doc://com.apple.documentation/documentation/UIKit/UIView] object in your SwiftUI interface. Adopt this protocol in one of your app’s custom instances, and use its methods to create, update, and tear down your view. The creation and update processes parallel the behavior of SwiftUI views, and you use them to configure your view with your app’s current state information. Use the teardown process to remove your view cleanly from your SwiftUI. For example, you might use the teardown process to notify other objects that the view is disappearing.

To add your view into your SwiftUI interface, create your [UIViewRepresentable](UIViewRepresentable.zh-Hans.md) instance and add it to your SwiftUI interface. The system calls the methods of your representable instance at appropriate times to create and update the view. The following example shows the inclusion of a custom `MyRepresentedCustomView` structure in the view hierarchy.

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

The system doesn’t automatically communicate changes occurring within your view to other parts of your SwiftUI interface. When you want your view to coordinate with other SwiftUI views, you must provide a [Coordinator](NSViewControllerRepresentable/Coordinator.zh-Hans.md) instance to facilitate those interactions. For example, you use a coordinator to forward target-action and delegate messages from your view to any SwiftUI views.



## Creating and updating the view

- **makeUIView(context:)**: Creates the view object and configures its initial state.
- **updateUIView(_:context:)**: Updates the state of the specified view with new information from SwiftUI.
- **UIViewRepresentable.Context**
- **UIViewType**: The type of view to present.

## Specifying a size

- **sizeThatFits(_:uiView:context:)**: Given a proposed size, returns the preferred size of the composite view.

## Cleaning up the view

- **dismantleUIView(_:coordinator:)**: Cleans up the presented UIKit view (and coordinator) in anticipation of their removal.

## Providing a custom coordinator object

- **makeCoordinator()**: Creates the custom instance that you use to communicate changes from your view to other parts of your SwiftUI interface.
- **Coordinator**: A type to coordinate with the view.

## Performing layout

- **UIViewRepresentable.LayoutOptions**

## Adding UIKit views to SwiftUI view hierarchies

- **UIViewRepresentableContext**: Contextual information about the state of the system that you use to create and update your UIKit view.
- **UIViewControllerRepresentable**: A view that represents a UIKit view controller.
- **UIViewControllerRepresentableContext**: Contextual information about the state of the system that you use to create and update your UIKit view controller.

## Inherits From

- View

