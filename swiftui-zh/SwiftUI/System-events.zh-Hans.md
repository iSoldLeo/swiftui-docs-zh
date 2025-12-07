--- 来源：https://developer.apple.com/documentation/SwiftUI/System-events
抓取时间：2025-12-02T17:41:27Z

---

# 系统事件

**API 集合**

响应系统事件，例如打开 URL。

## 概述

指定视图和场景修饰符，以指示您的应用如何响应某些系统事件。例如，您可以使用 [onOpenURL(perform:)](View/onOpenURL_perform.zh-Hans.md) 视图修饰符来定义应用收到通用链接时要执行的操作，或者使用 [backgroundTask(_:action:)](scene/backgroundTask___action.zh-Hans.md) 场景修饰符来指定响应后台任务事件（例如后台 URL 会话完成）而要执行的异步任务。

## 发送和接收用户活动

- **使用 SwiftUI 恢复应用状态**：通过保留用户当前活动，为用户提供应用连续性。

- **userActivity(_:element:_:)**：声明用户活动类型。

- **userActivity(_:isActive:_:)**：声明用户活动类型。

- **onContinueUserActivity(_:perform:)**：注册一个处理程序，用于响应应用接收到的用户活动。

## 发送和接收 URL

- **openURL**：打开 URL 的操作。

- **OpenURLAction**：打开 URL 的操作。

- **onOpenURL(perform:)**：注册一个处理程序，用于响应应用接收到的 URL。

## 处理外部事件

- **handlesExternalEvents(matching:)**：指定 SwiftUI 会为哪些外部事件打开已修改场景的新实例。

- **handlesExternalEvents(preferring:allowing:)**：指定视图场景在已打开时处理的外部事件。

## 处理后台任务

- **backgroundTask(_:action:)**：当系统提供后台任务时，运行指定的操作。

- **BackgroundTask**：您的应用或扩展程序可以处理的后台任务类型。

- **SnapshotData**：快照后台任务的关联数据。

- **SnapshotResponse**：您的应用对快照后台任务的响应。

## 导入和导出可传输项目

- **importableFromServices(for:action:)**：启用从服务（例如 macOS 上的“连续互通相机”）导入项目。

- **exportableToServices(_:)**：导出项目以供快捷指令、快速操作和服务使用。

- **exportableToServices(_:onEdit:)**：导出可供快捷指令、快速操作和服务使用的读写项目。

## 使用项目提供程序导入和导出

- **importsItemProviders(_:onImport:)**：启用从服务（例如 macOS 上的“连续互通相机”）导入项目提供程序的功能。

- **exportsItemProviders(_:onExport:)**：导出可供快捷指令、快速操作和服务使用的只读项目提供程序。

- **exportsItemProviders(_:onExport:onEdit:)**：导出可供快捷指令、快速操作和服务使用的读写项目提供程序。

## 事件处理

- **Gestures**：定义从轻点、点击和滑动到更精细的手势的各种交互方式。

- **输入事件**：响应来自硬件设备（例如键盘或触控栏）的输入。

- **Clipboard**：允许用户通过发出复制和粘贴命令来移动或复制项目。

- **拖放**：允许用户通过将项目从一个位置拖动到另一个位置来移动或复制项目。

- **Focus**：识别并控制哪些可见对象响应用户交互。


---
source: https://developer.apple.com/documentation/SwiftUI/System-events
crawled: 2025-12-02T17:41:27Z
---

# System events

**API Collection**

React to system events, like opening a URL.

## Overview

Specify view and scene modifiers to indicate how your app responds to certain system events. For example, you can use the [onOpenURL(perform:)](View/onOpenURL_perform.zh-Hans.md) view modifier to define an action to take when your app receives a universal link, or use the [backgroundTask(_:action:)](scene/backgroundTask___action.zh-Hans.md) scene modifier to specify an asynchronous task to carry out in response to a background task event, like the completion of a background URL session.



## Sending and receiving user activities

- **Restoring your app’s state with SwiftUI**: Provide app continuity for users by preserving their current activities.
- **userActivity(_:element:_:)**: Advertises a user activity type.
- **userActivity(_:isActive:_:)**: Advertises a user activity type.
- **onContinueUserActivity(_:perform:)**: Registers a handler to invoke in response to a user activity that your app receives.

## Sending and receiving URLs

- **openURL**: An action that opens a URL.
- **OpenURLAction**: An action that opens a URL.
- **onOpenURL(perform:)**: Registers a handler to invoke in response to a URL that your app receives.

## Handling external events

- **handlesExternalEvents(matching:)**: Specifies the external events for which SwiftUI opens a new instance of the modified scene.
- **handlesExternalEvents(preferring:allowing:)**: Specifies the external events that the view’s scene handles if the scene is already open.

## Handling background tasks

- **backgroundTask(_:action:)**: Runs the specified action when the system provides a background task.
- **BackgroundTask**: The kinds of background tasks that your app or extension can handle.
- **SnapshotData**: The associated data of a snapshot background task.
- **SnapshotResponse**: Your application’s response to a snapshot background task.

## Importing and exporting transferable items

- **importableFromServices(for:action:)**: Enables importing items from services, such as Continuity Camera on macOS.
- **exportableToServices(_:)**: Exports items for consumption by shortcuts, quick actions, and services.
- **exportableToServices(_:onEdit:)**: Exports read-write items for consumption by shortcuts, quick actions, and services.

## Importing and exporting using item providers

- **importsItemProviders(_:onImport:)**: Enables importing item providers from services, such as Continuity Camera on macOS.
- **exportsItemProviders(_:onExport:)**: Exports a read-only item provider for consumption by shortcuts, quick actions, and services.
- **exportsItemProviders(_:onExport:onEdit:)**: Exports a read-write item provider for consumption by shortcuts, quick actions, and services.

## Event handling

- **Gestures**: Define interactions from taps, clicks, and swipes to fine-grained gestures.
- **Input events**: Respond to input from a hardware device, like a keyboard or a Touch Bar.
- **Clipboard**: Enable people to move or duplicate items by issuing Copy and Paste commands.
- **Drag and drop**: Enable people to move or duplicate items by dragging them from one location to another.
- **Focus**: Identify and control which visible object responds to user interaction.

