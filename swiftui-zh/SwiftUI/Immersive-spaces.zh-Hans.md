---
来源： https://developer.apple.com/documentation/SwiftUI/Immersive-spaces
抓取时间： 2025-12-02T17:20:43Z
---

# 沉浸式空间

** 应用程序集**

在人的周围显示无限制的内容。

### 概览

在 visionOS 中使用沉浸式空间来展示任何容器之外的 SwiftUI 视图。您可以在空间中包含任何视图，不过您通常会使用 [doc://com.apple.documentation/documentation/RealityKit/RealityView] 来展示 RealityKit 内容。



你可以使用[immersionStyle(selection:in:)](Scene/immersionStyle_selection_in.zh-Hans.md) 场景修饰符请求三种风格之一的空间：

- [mixed](ImmersionStyle/mixed.zh-Hans.md)风格将您的内容与穿透融合在一起。这样，您就可以在人物周围放置虚拟对象。
- [full](ImmersionStyle/full.zh-Hans.md)样式只显示您的内容，并关闭透视功能。这样，您就可以完全控制视觉体验，比如将人们带入一个新世界。
- [progressive](ImmersionStyle/progressive.zh-Hans.md)样式完全取代了部分显示屏的透传功能。您可以使用这种样式让人们立足于现实世界，同时显示另一个世界的景象。

当你打开沉浸式空间时，系统会继续显示你的应用程序的所有窗口，但会隐藏其他应用程序的窗口。系统支持在所有应用程序中一次只显示一个空间，因此只有当一个空间尚未打开时，您的应用程序才能打开一个空间。

## 创建沉浸式空间

- **ImmersiveSpace**：在无边界空间中呈现内容的场景。
- **ImmersiveSpaceContentBuilder**：用于合成沉浸式空间元素集合的结果生成器。
- **immersionStyle(selection:in:)**：设置沉浸式空间的样式。
- **ImmersionStyle**：身临其境空间可具有的样式。
- **immersiveSpaceDisplacement**：将沉浸式空间从其默认位置移开时，系统应用于该空间的位移，以米为单位。
- **ImmersiveEnvironmentBehavior**：当您的应用程序打开一个场景时，系统提供的沉浸式环境的行为。
- **ProgressiveImmersionAspectRatio**：当您的应用程序打开场景时，系统提供的沉浸式环境的行为。

## 打开沉浸式空间

- **openImmersiveSpace**：呈现沉浸式空间的动作。
- **OpenImmersiveSpaceAction**：呈现身临其境空间的动作。

## 关闭沉浸式空间

- **dismissImmersiveSpace**：存储在视图环境中的沉浸式空间关闭动作。
- **DismissImmersiveSpaceAction**：解除沉浸式空间的动作。

## 在沉浸期间隐藏上肢

- **upperLimbVisibility(_:)**：在呈现[ImmersiveSpace](ImmersiveSpace.zh-Hans.md)场景时，设置用户上肢的首选可见度。
- **upperLimbVisibility(_:)**：设置在显示[ImmersiveSpace](ImmersiveSpace.zh-Hans.md) 场景时用户上肢的首选可见度。

## 调整内容亮度

- **immersiveContentBrightness(_:)**：设置沉浸式空间的内容亮度。
- **ImmersiveContentBrightness**：身临其境空间的内容亮度。

## 响应沉浸变化

- **onImmersionChange(initial:_:)**：当应用程序的沉浸状态发生变化时执行操作。
- **ImmersionChangeContext**：表示应用程序沉浸状态的结构。

## 在沉浸式空间中添加菜单项

- **immersiveEnvironmentPicker(content:)**：从媒体播放器的环境选择器中添加菜单项以打开沉浸式空间。

## 处理远程沉浸式空间

- **RemoteImmersiveSpace**：在远程设备的无界空间中呈现内容的场景。
- **RemoteDeviceIdentifier**：不透明类型，用于标识在[RemoteImmersiveSpace](RemoteImmersiveSpace.zh-Hans.md)中显示场景内容的远程设备。

## 应用程序结构

- 应用程序组织**：定义应用程序的入口点和顶层结构。
- **Scenes**：声明构成应用程序各部分的用户界面分组。
- **Windows**：在窗口或窗口集合中显示用户界面内容。
- **Documents**：使人们能够打开和管理文件。
- **Navigation**：使人们能够在场景中的应用程序视图层次结构的不同部分之间移动。
- **模拟演示**：在单独的视图中展示内容，提供集中的交互。
- **Toolbars**：提供对常用命令和控件的即时访问。
- **Search**：使人们能够在您的应用程序中搜索文本或其他内容。
- ** 应用程序扩展**：将应用程序的基本功能扩展到系统的其他部分，如添加 Widget。


---
source: https://developer.apple.com/documentation/SwiftUI/Immersive-spaces
crawled: 2025-12-02T17:20:43Z
---

# Immersive spaces

**API Collection**

Display unbounded content in a person’s surroundings.

## Overview

Use an immersive space in visionOS to present SwiftUI views outside of any containers. You can include any views in a space, although you typically use a [doc://com.apple.documentation/documentation/RealityKit/RealityView] to present RealityKit content.



You can request one of three styles of spaces with the [immersionStyle(selection:in:)](Scene/immersionStyle_selection_in.zh-Hans.md) scene modifier:

- The [mixed](ImmersionStyle/mixed.zh-Hans.md) style blends your content with passthrough. This enables you to place virtual objects in a person’s surroundings.
- The [full](ImmersionStyle/full.zh-Hans.md) style displays only your content, with passthrough turned off. This enables you to completely control the visual experience, like when you want to transport people to a new world.
- The [progressive](ImmersionStyle/progressive.zh-Hans.md) style completely replaces passthrough in a portion of the display. You might use this style to keep people grounded in the real world while displaying a view into another world.

When you open an immersive space, the system continues to display all of your app’s windows, but hides windows from other apps. The system supports displaying only one space at a time across all apps, so your app can only open a space if one isn’t already open.

## Creating an immersive space

- **ImmersiveSpace**: A scene that presents its content in an unbounded space.
- **ImmersiveSpaceContentBuilder**: A result builder for composing a collection of immersive space elements.
- **immersionStyle(selection:in:)**: Sets the style for an immersive space.
- **ImmersionStyle**: The styles that an immersive space can have.
- **immersiveSpaceDisplacement**: The displacement that the system applies to the immersive space when moving the space away from its default position, in meters.
- **ImmersiveEnvironmentBehavior**: The behavior of the system-provided immersive environments when a scene is opened by your app.
- **ProgressiveImmersionAspectRatio**

## Opening an immersive space

- **openImmersiveSpace**: An action that presents an immersive space.
- **OpenImmersiveSpaceAction**: An action that presents an immersive space.

## Closing the immersive space

- **dismissImmersiveSpace**: An immersive space dismissal action stored in a view’s environment.
- **DismissImmersiveSpaceAction**: An action that dismisses an immersive space.

## Hiding upper limbs during immersion

- **upperLimbVisibility(_:)**: Sets the preferred visibility of the user’s upper limbs, while an [ImmersiveSpace](ImmersiveSpace.zh-Hans.md) scene is presented.
- **upperLimbVisibility(_:)**: Sets the preferred visibility of the user’s upper limbs, while an [ImmersiveSpace](ImmersiveSpace.zh-Hans.md) scene is presented.

## Adjusting content brightness

- **immersiveContentBrightness(_:)**: Sets the content brightness of an immersive space.
- **ImmersiveContentBrightness**: The content brightness of an immersive space.

## Responding to immersion changes

- **onImmersionChange(initial:_:)**: Performs an action when the immersion state of your app changes.
- **ImmersionChangeContext**: A structure that represents a state of immersion of your app.

## Adding menu items to an immersive space

- **immersiveEnvironmentPicker(content:)**: Add menu items to open immersive spaces from a media player’s environment picker.

## Handling remote immersive spaces

- **RemoteImmersiveSpace**: A scene that presents its content in an unbounded space on a remote device.
- **RemoteDeviceIdentifier**: An opaque type that identifies a remote device displaying scene content in a [RemoteImmersiveSpace](RemoteImmersiveSpace.zh-Hans.md).

## App structure

- **App organization**: Define the entry point and top-level structure of your app.
- **Scenes**: Declare the user interface groupings that make up the parts of your app.
- **Windows**: Display user interface content in a window or a collection of windows.
- **Documents**: Enable people to open and manage documents.
- **Navigation**: Enable people to move between different parts of your app’s view hierarchy within a scene.
- **Modal presentations**: Present content in a separate view that offers focused interaction.
- **Toolbars**: Provide immediate access to frequently used commands and controls.
- **Search**: Enable people to search for text or other content within your app.
- **App extensions**: Extend your app’s basic functionality to other parts of the system, like by adding a Widget.

