---
来源： https://developer.apple.com/documentation/swiftui/wkinterfaceobjectrepresentable
抓取时间： 2025-12-04T11:33:46Z
---

# WKInterfaceObjectRepresentable

**Protocol**

表示 WatchKit 接口对象的视图。

## 声明

```swift
@MainActor @preconcurrency protocol WKInterfaceObjectRepresentable : View where Self.Body == Never
```

## 概览

在 SwiftUI 界面中使用`WKInterfaceObjectRepresentable` 实例来创建和管理[doc://com.apple.documentation/documentation/WatchKit/WKInterfaceObject]。在您应用程序的一个自定义实例中采用此协议，并使用其方法来创建、更新和删除您的界面对象。创建和更新过程与 SwiftUI 视图的行为类似，您可以使用它们将界面对象配置为应用程序的当前状态信息。使用拆卸流程可以从 SwiftUI 中干净利落地移除界面对象。例如，您可以使用拆卸流程通知应用程序的其他部分界面对象即将消失。

要将界面对象添加到 SwiftUI 界面中，请创建您的`WKInterfaceObjectRepresentable` 实例并将其添加到 SwiftUI 界面中。系统会在适当的时候调用您的可表示实例的方法来创建和更新接口对象。

系统不会自动将界面对象中发生的更改传达给 SwiftUI 界面的其他部分。当您希望您的界面对象与其他 SwiftUI 视图协调时，您必须提供一个 [Coordinator](WKInterfaceObjectRepresentable/Coordinator.zh-Hans.md) 实例来促进这些交互。例如，您可以使用协调器将您的接口对象的 target-action 和委托消息转发给任何 SwiftUI 视图。

## 创建和更新接口对象

- **makeWKInterfaceObject(context:)**：创建 WatchKit 接口对象并配置其初始状态。
- **updateWKInterfaceObject(_:context:)**：将呈现的 WatchKit 接口对象（及其协调器）更新为最新配置。
- **WKInterfaceObjectRepresentable.Context**

## 清理接口对象

- **dismantleWKInterfaceObject(_:coordinator:)**：清理呈现的 WatchKit 接口对象（及其协调器），以备移除。

## 提供自定义协调器对象

- **makeCoordinator()**：创建自定义实例，用于将界面对象的更改传达给 SwiftUI 界面的其他部分。
- **Coordinator**：用于与 WatchKit 界面对象协调的类型。
- **WKInterfaceObjectType**：要显示的 WatchKit 接口对象的类型。

## 将 WatchKit 视图添加到 SwiftUI 视图层次结构中

- **WKInterfaceObjectRepresentableContext**：有关系统状态的上下文信息，用于创建和更新 WatchKit 界面对象。

## 继承自

- 查看


---
source: https://developer.apple.com/documentation/swiftui/wkinterfaceobjectrepresentable
crawled: 2025-12-04T11:33:46Z
---

# WKInterfaceObjectRepresentable

**Protocol**

A view that represents a WatchKit interface object.

## Declaration

```swift
@MainActor @preconcurrency protocol WKInterfaceObjectRepresentable : View where Self.Body == Never
```

## Overview

Use a `WKInterfaceObjectRepresentable` instance to create and manage a [doc://com.apple.documentation/documentation/WatchKit/WKInterfaceObject] in your SwiftUI interface. Adopt this protocol in one of your app’s custom instances, and use its methods to create, update, and tear down your interface object. The creation and update processes parallel the behavior of SwiftUI views, and you use them to configure your interface object with your app’s current state information. Use the teardown process to remove your interface object cleanly from your SwiftUI. For example, you might use the teardown process to notify other parts of your app that the interface object is disappearing.

To add your interface object into your SwiftUI interface, create your `WKInterfaceObjectRepresentable` instance and add it to your SwiftUI interface. The system calls the methods of your representable instance at appropriate times to create and update the interface object.

The system doesn’t automatically communicate changes occurring within your interface object to other parts of your SwiftUI interface. When you want your interface object to coordinate with other SwiftUI views, you must provide a [Coordinator](WKInterfaceObjectRepresentable/Coordinator.zh-Hans.md) instance to facilitate those interactions. For example, you use a coordinator to forward target-action and delegate messages from your interface object to any SwiftUI views.

## Creating and updating the interface object

- **makeWKInterfaceObject(context:)**: Creates a WatchKit interface object and configures its initial state.
- **updateWKInterfaceObject(_:context:)**: Updates the presented WatchKit interface object (and its coordinator) to the latest configuration.
- **WKInterfaceObjectRepresentable.Context**

## Cleaning up the interface object

- **dismantleWKInterfaceObject(_:coordinator:)**: Cleans up the presented WatchKit interface object (and its coordinator) in anticipation of their removal.

## Providing a custom coordinator object

- **makeCoordinator()**: Creates the custom instance that you use to communicate changes from your interface object to other parts of your SwiftUI interface.
- **Coordinator**: A type to coordinate with the WatchKit interface object.
- **WKInterfaceObjectType**: The type of WatchKit interface object to be presented.

## Adding WatchKit views to SwiftUI view hierarchies

- **WKInterfaceObjectRepresentableContext**: Contextual information about the state of the system that you use to create and update your WatchKit interface object.

## Inherits From

- View

