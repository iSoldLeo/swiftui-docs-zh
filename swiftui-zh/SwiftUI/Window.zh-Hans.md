---
来源： https://developer.apple.com/documentation/SwiftUI/Window
抓取时间： 2025-12-02T17:20:59Z
---

# 窗口

**Structure**

在单一、独特窗口中显示内容的场景。

## 声明

```swift
struct Window<Content> where Content : View
```

## 概览

使用`Window`场景可通过一个窗口来增强应用程序的主界面，使人们可以访问补充功能。例如，您可以在邮件阅读器应用程序中创建一个辅助窗口，使用户可以查看其帐户连接的状态：

```swift
 @main
 struct Mail: App {
     var body: some Scene {
         WindowGroup {
             MailViewer()
         }
         Window("Connection Doctor", id: "connection-doctor") {
             ConnectionDoctor()
         }
     }
 }
```

提供一个标题作为窗口初始化器的第一个参数。系统将使用标题在窗口标题栏或 Windows 菜单自动显示的可用单例窗口列表中向使用您应用程序的用户标识该窗口。





### 以编程方式打开窗口

人们可以通过在 Windows 菜单中选择窗口来打开窗口，但也可以使用从环境中读取的 [openWindow](EnvironmentValues/openWindow.zh-Hans.md) 操作以编程方式打开窗口。使用初始化窗口时使用的`id` 参数来指示打开哪个窗口。例如，您可以创建一个按钮来打开上一个示例中的窗口：

```swift
struct OpenConnectionDoctorButton: View {
    @Environment(\.openWindow) private var openWindow

    var body: some View {
        Button("Connection doctor") {
            openWindow(id: "connection-doctor") // Match the window's identifier.
        }
    }
}
```

如果调用该操作时窗口已经打开，则该操作会将打开的窗口置于最前面。请确保在您定义的所有 `Window` 和 [WindowGroup](WindowGroup.zh-Hans.md) 实例中使用唯一的标识符。

### 以编程方式关闭窗口

系统为用户提供了关闭窗口的控件，但您也可以在窗口的视图层次结构中使用 [dismiss](EnvironmentValues/dismiss.zh-Hans.md) 操作以编程方式关闭窗口。例如，你可以在连接医生视图中加入一个按钮，用来关闭视图：

```swift
struct ConnectionDoctor: View {
    @Environment(\.dismiss) private var dismiss

    var body: some View {
        VStack {
            // ...

            Button("Dismiss") {
                dismiss()
            }
        }
    }
}
```

如果从窗口内显示的模式窗体（如工作表或弹出窗口）中调用 "驳回 "操作，则不会关闭窗口。在这种情况下，该操作将关闭模态演示。

### 使用窗口作为主场景

在不适合使用多窗口功能时，您可以使用窗口作为应用程序的主场景。例如，对于一个依赖于摄像头等硬件资源的视频通话应用程序来说，显示一个以上的窗口可能并不合理：

```swift
@main
struct VideoCall: App {
    var body: some Scene {
        Window("VideoCall", id: "main") {
            CameraView()
        }
    }
}
```

如果您的应用程序使用单个窗口作为主场景，则窗口关闭时应用程序会退出。这种行为不同于使用[WindowGroup](WindowGroup.zh-Hans.md) 作为主场景的应用程序，在后者中，即使关闭了所有窗口，应用程序仍会继续运行。



## 创建窗口

- **init(_:id:content:)**：创建带有标题和标识符的窗口。

## 创建窗口

- **WindowGroup**：显示一组结构相同窗口的场景。
- **UtilityWindow**：专门的窗口场景，为应用程序的主场景内容提供辅助功能。
- **WindowStyle**：窗口的外观和交互规范。
- **windowStyle(_:)**：设置此场景创建的窗口的样式。

## 符合

- 场景


---
source: https://developer.apple.com/documentation/SwiftUI/Window
crawled: 2025-12-02T17:20:59Z
---

# Window

**Structure**

A scene that presents its content in a single, unique window.

## Declaration

```swift
struct Window<Content> where Content : View
```

## Overview

Use a `Window` scene to augment the main interface of your app with a window that gives people access to supplemental functionality. For example, you can create a secondary window in a mail reader app that enables people to view the status of their account connections:

```swift
 @main
 struct Mail: App {
     var body: some Scene {
         WindowGroup {
             MailViewer()
         }
         Window("Connection Doctor", id: "connection-doctor") {
             ConnectionDoctor()
         }
     }
 }
```

Provide a title as the first argument to the window’s intializer. The system uses the title to identify the window to people using your app in the window’s title bar or in the list of available singleton windows that the Windows menu displays automatically.





### Open a window programmatically

People open the window by selecting it in the Windows menu, but you can also open the window programmatically using the [openWindow](EnvironmentValues/openWindow.zh-Hans.md) action that you read from the environment. Use the `id` parameter that you initialize the window with to indicate which window to open. For example, you can create a button to open the window from the previous example:

```swift
struct OpenConnectionDoctorButton: View {
    @Environment(\.openWindow) private var openWindow

    var body: some View {
        Button("Connection doctor") {
            openWindow(id: "connection-doctor") // Match the window's identifier.
        }
    }
}
```

If the window is already open when you call this action, the action brings the open window to the front. Be sure to use unique identifiers across all of the `Window` and [WindowGroup](WindowGroup.zh-Hans.md) instances that you define.

### Dismiss a window programmatically

The system provides people with controls to close windows, but you can also close a window programmatically using the [dismiss](EnvironmentValues/dismiss.zh-Hans.md) action from within the window’s view hierarchy. For example, you can include a button in the connection doctor view that dismisses the view:

```swift
struct ConnectionDoctor: View {
    @Environment(\.dismiss) private var dismiss

    var body: some View {
        VStack {
            // ...

            Button("Dismiss") {
                dismiss()
            }
        }
    }
}
```

The dismiss action doesn’t close the window if you call it from a modal — like a sheet or a popover — that you present from within the window. In that case, the action dismisses the modal presentation instead.

### Use a window as the main scene

You can use a window as the main scene of your app when multi-window functionality isn’t appropriate. For example, it might not make sense to display more than one window for a video call app that relies on a hardware resource, like a camera:

```swift
@main
struct VideoCall: App {
    var body: some Scene {
        Window("VideoCall", id: "main") {
            CameraView()
        }
    }
}
```

If your app uses a single window as its primary scene, the app quits when the window closes. This behavior differs from an app that uses a [WindowGroup](WindowGroup.zh-Hans.md) as its primary scene, where the app continues to run even after closing all of its windows.



## Creating a window

- **init(_:id:content:)**: Creates a window with a title and an identifier.

## Creating windows

- **WindowGroup**: A scene that presents a group of identically structured windows.
- **UtilityWindow**: A specialized window scene that provides secondary utility to the content of the main scenes of an application.
- **WindowStyle**: A specification for the appearance and interaction of a window.
- **windowStyle(_:)**: Sets the style for windows created by this scene.

## Conforms To

- Scene

