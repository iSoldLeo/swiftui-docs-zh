--- 来源：https://developer.apple.com/documentation/SwiftUI/Windows
抓取时间：2025-12-02T17:20:43Z

---

# Windows

**API 集合**

在单个窗口或窗口集合中显示用户界面内容。

## 概述

在应用界面中呈现视图层级的最常用方法是使用 [WindowGroup](WindowGroup.zh-Hans.md)，它会生成特定于平台的行为和外观。

在支持的平台上，用户可以同时打开该组中的多个窗口。每个窗口都依赖于相同的根视图定义，但保留各自的视图状态。在某些平台上，您还可以使用 [Window](Window.zh-Hans.md) 场景类型，通过单实例窗口来补充应用的用户界面。

使用添加到窗口声明中的场景修饰符（例如 [windowStyle(_:)](scene/windowStyle.zh-Hans.md) 或 [defaultPosition(_:)](scene/defaultPosition.zh-Hans.md)）来配置窗口。您还可以通过将 [presentedWindowStyle(_:)](View/presentedWindowStyle.zh-Hans.md) 视图修饰符添加到视图层级结构中的视图，来指定如何配置从视图层级结构呈现的新窗口。

有关设计指南，请参阅《人机界面指南》中的 [doc://com.apple.documentation/design/Human-Interface-Guidelines/windows]。

## 基本功能

- **在 macOS 中自定义窗口样式和状态恢复行为**：配置应用程序窗口在 macOS 中的外观和功能，以提供更具吸引力和一致性的用户体验。

- **在 SwiftUI 应用程序中添加多个窗口**：通过响应状态更改来组合丰富的视图，并自定义应用程序在 iPadOS 和 macOS 上的场景呈现和行为。

## 创建窗口

- **WindowGroup**：用于呈现一组结构相同的窗口的场景。

- **Window**：用于在单个窗口中呈现其内容的场景。

- **UtilityWindow**：用于为应用程序主场景的内容提供辅助功能的专用窗口场景。

- **WindowStyle**：用于定义窗口外观和交互方式的规范。

- **windowStyle(_:)**：用于设置此场景创建的窗口的样式。

## 设置关联工具栏的样式

- **windowToolbarStyle(_:)**：用于设置此场景中定义的工具栏的样式。

- **windowToolbarLabelStyle(_:)**：用于设置工具栏中项目的标签样式，并允许用户自定义。

- **windowToolbarLabelStyle(fixed:)**：设置工具栏中项目的标签样式。

- **WindowToolbarStyle**：窗口工具栏的外观和行为规范。

## 打开窗口

- **呈现窗口和空间**：打开和关闭构成应用程序界面的场景。

- **supportsMultipleWindows**：一个布尔值，指示当前平台是否支持打开多个窗口。

- **openWindow**：存储在视图环境中的窗口呈现操作。

- **OpenWindowAction**：呈现窗口的操作。

- **PushWindowAction**：将请求的窗口替换调用该操作的窗口的操作。

## 关闭窗口

- **dismissWindow**：存储在视图环境中的窗口关闭操作。

- **DismissWindowAction**：关闭与特定场景关联的窗口的操作。

- **dismiss**：关闭当前演示的操作。

- **DismissAction**：关闭演示的操作。

- **DismissBehavior**：程序化的窗口关闭行为。

## 调整窗口大小

- **定位和调整窗口大小**：影响应用程序呈现的窗口的初始几何形状。

- **defaultSize(_:)**：设置窗口的默认大小。

- **defaultSize(width:height:)**：设置窗口的默认宽度和高度。

- **defaultSize(width:height:depth:)**：设置体积窗口的默认大小。

- **defaultSize(_:in:)**：设置体积窗口的默认大小。

- **defaultSize(width:height:depth:in:)**：设置体积窗口的默认大小。

- **windowResizability(_:)**：设置窗口的可调整大小类型。

- **WindowResizability**：窗口的可调整大小。

- **windowIdealSize(_:)**：指定从此场景派生的窗口在缩放时如何确定其大小。

- **WindowIdealSize**：定义窗口在缩放时应使用的大小的类型。

## 定位窗口

- **defaultPosition(_:)**：设置窗口的默认位置。

- **WindowLevel**：窗口级别。

- **windowLevel(_:)**：设置此场景的窗口级别。

- **WindowLayoutRoot**：表示窗口根内容的代理。

- **WindowPlacement**：表示窗口首选大小和位置的类型。

- **defaultWindowPlacement(_:)**：定义用于确定窗口默认位置的函数。

- **windowIdealPlacement(_:)**：提供一个函数，用于确定场景窗口缩放时使用的位置。

- **WindowPlacementContext**：表示用于调整窗口大小和位置的上下文信息的类型。

- **WindowProxy**：应用程序中已打开窗口的代理。

- **DisplayProxy**：提供有关显示硬件信息的类型。

## 配置窗口可见性

- **WindowVisibilityToggle**：用于切换窗口可见性的专用按钮。

- **defaultLaunchBehavior(_:)**：设置此场景的默认启动行为。

- **restorationBehavior(_:)**：设置此场景的恢复行为。

- **SceneLaunchBehavior**：场景的启动行为。

- **SceneRestorationBehavior**：场景的恢复行为。

- **persistentSystemOverlays(_:)**：设置覆盖在应用程序上的非瞬态系统视图的首选可见性。

- **windowToolbarFullScreenVisibility(_:)**：配置窗口进入全屏模式时窗口工具栏的可见性。

- **WindowToolbarFullScreenVisibility**：窗口工具栏在全屏模式下的可见性。

## 管理窗口行为

- **WindowManagerRole**：用于定义场景窗口在受管窗口上下文（例如全屏模式和舞台管理器）中使用时的行为选项。

- **windowManagerRole(_:)**：配置从 `self` 派生的窗口在参与受管窗口上下文（例如全屏或舞台管理器）时的角色。

- **WindowInteractionBehavior**：用于启用和禁用窗口交互行为的选项。

- **windowDismissBehavior(_:)**：配置包含 `self` 的窗口的关闭功能。

- **windowFullScreenBehavior(_:)**：配置包含 `self` 的窗口的全屏功能。

- **windowMinimizeBehavior(_:)**：配置包含 `self` 的窗口的最小化功能。

- **windowResizeBehavior(_:)**：配置包含 `self` 的窗口的调整大小功能。

- **windowBackgroundDragBehavior(_:)**：配置拖动窗口背景的行为。

## 与卷交互

- **onVolumeViewpointChange(updateStrategy:initial:_:)**：添加卷的视点改变时要执行的操作。

- **supportedVolumeViewpoints(_:)**：指定卷中的窗口栏和装饰条支持哪些视点。

- **VolumeViewpointUpdateStrategy**：描述何时调用提供给 [onVolumeViewpointChange(updateStrategy:initial:_:)](View/onVolumeViewpointChange_updateStrategy_initial.zh-Hans.md) 的动作的类型。

- **Viewpoint3D**：描述观察方向的类型。

- **SquareAzimuth**：描述沿水平面观察方向的类型，并捕捉到四个方向。

- **WorldAlignmentBehavior**：表示场景的世界对齐行为的类型。

- **volumeWorldAlignment(_:)**：指定在世界中移动时体积的对齐方式。

- **WorldScalingBehavior**：指定窗口在世界中的缩放行为。

- **defaultWorldScaling(_:)**：指定窗口的世界缩放行为。

- **WorldScalingCompensation**：指示返回的指标是否会考虑动态缩放。

- **worldTrackingLimitations**：设备当前跟踪用户周围环境的限制。

- **WorldTrackingLimitation**：用于表示跟踪用户周围环境限制的结构。

- **SurfaceSnappingInfo**：表示窗口场景吸附状态信息的类型。

## 已弃用类型

- **ControlActiveState**：窗口中控件的预期活动外观。

## 应用结构

- **应用组织结构**：定义应用的入口点和顶层结构。

- **Scenes**：声明构成应用各个部分的用户界面分组。

- **沉浸式空间**：在用户的周围环境中显示无边界的内容。

- **Documents**：允许用户打开和管理文档。

- **Navigation**：允许用户在场景内的应用视图层级结构的不同部分之间切换。

- **模态呈现**：在单独的视图中呈现内容，提供专注的交互体验。

- **Toolbars**：提供对常用命令和控件的快速访问。

- **Search**：允许用户在应用内搜索文本或其他内容。

- **应用扩展**：将应用的基本功能扩展到系统的其他部分，例如通过添加小部件。


---
source: https://developer.apple.com/documentation/SwiftUI/Windows
crawled: 2025-12-02T17:20:43Z
---

# Windows

**API Collection**

Display user interface content in a window or a collection of windows.

## Overview

The most common way to present a view hierarchy in your app’s interface is with a [WindowGroup](WindowGroup.zh-Hans.md), which produces a platform-specific behavior and appearance.



On platforms that support it, people can open multiple windows from the group simultaneously. Each window relies on the same root view definition, but retains its own view state. On some platforms, you can also supplement your app’s user interface with a single-instance window using the [Window](Window.zh-Hans.md) scene type.

Configure windows using scene modifiers that you add to the window declaration, like [windowStyle(_:)](scene/windowStyle.zh-Hans.md) or [defaultPosition(_:)](scene/defaultPosition.zh-Hans.md). You can also indicate how to configure new windows that you present from a view hierarchy by adding the [presentedWindowStyle(_:)](View/presentedWindowStyle.zh-Hans.md) view modifier to a view in the hierarchy.

For design guidance, see [doc://com.apple.documentation/design/Human-Interface-Guidelines/windows] in the Human Interface Guidelines.

## Essentials

- **Customizing window styles and state-restoration behavior in macOS**: Configure how your app’s windows look and function in macOS to provide an engaging and more coherent experience.
- **Bringing multiple windows to your SwiftUI app**: Compose rich views by reacting to state changes and customize your app’s scene presentation and behavior on iPadOS and macOS.

## Creating windows

- **WindowGroup**: A scene that presents a group of identically structured windows.
- **Window**: A scene that presents its content in a single, unique window.
- **UtilityWindow**: A specialized window scene that provides secondary utility to the content of the main scenes of an application.
- **WindowStyle**: A specification for the appearance and interaction of a window.
- **windowStyle(_:)**: Sets the style for windows created by this scene.

## Styling the associated toolbar

- **windowToolbarStyle(_:)**: Sets the style for the toolbar defined within this scene.
- **windowToolbarLabelStyle(_:)**: Sets the label style of items in a toolbar and enables user customization.
- **windowToolbarLabelStyle(fixed:)**: Sets the label style of items in a toolbar.
- **WindowToolbarStyle**: A specification for the appearance and behavior of a window’s toolbar.

## Opening windows

- **Presenting windows and spaces**: Open and close the scenes that make up your app’s interface.
- **supportsMultipleWindows**: A Boolean value that indicates whether the current platform supports opening multiple windows.
- **openWindow**: A window presentation action stored in a view’s environment.
- **OpenWindowAction**: An action that presents a window.
- **PushWindowAction**: An action that opens the requested window in place of the window the action is called from.

## Closing windows

- **dismissWindow**: A window dismissal action stored in a view’s environment.
- **DismissWindowAction**: An action that dismisses a window associated to a particular scene.
- **dismiss**: An action that dismisses the current presentation.
- **DismissAction**: An action that dismisses a presentation.
- **DismissBehavior**: Programmatic window dismissal behaviors.

## Sizing a window

- **Positioning and sizing windows**: Influence the initial geometry of windows that your app presents.
- **defaultSize(_:)**: Sets a default size for a window.
- **defaultSize(width:height:)**: Sets a default width and height for a window.
- **defaultSize(width:height:depth:)**: Sets a default size for a volumetric window.
- **defaultSize(_:in:)**: Sets a default size for a volumetric window.
- **defaultSize(width:height:depth:in:)**: Sets a default size for a volumetric window.
- **windowResizability(_:)**: Sets the kind of resizability to use for a window.
- **WindowResizability**: The resizability of a window.
- **windowIdealSize(_:)**: Specifies how windows derived form this scene should determine their size when zooming.
- **WindowIdealSize**: A type which defines the size a window should use when zooming.

## Positioning a window

- **defaultPosition(_:)**: Sets a default position for a window.
- **WindowLevel**: The level of a window.
- **windowLevel(_:)**: Sets the window level of this scene.
- **WindowLayoutRoot**: A proxy which represents the root contents of a window.
- **WindowPlacement**: A type which represents a preferred size and position for a window.
- **defaultWindowPlacement(_:)**: Defines a function used for determining the default placement of windows.
- **windowIdealPlacement(_:)**: Provides a function which determines a placement to use when windows of a scene zoom.
- **WindowPlacementContext**: A type which represents contextual information used for sizing and positioning windows.
- **WindowProxy**: The proxy for an open window in the app.
- **DisplayProxy**: A type which provides information about display hardware.

## Configuring window visibility

- **WindowVisibilityToggle**: A specialized button for toggling the visibility of a window.
- **defaultLaunchBehavior(_:)**: Sets the default launch behavior for this scene.
- **restorationBehavior(_:)**: Sets the restoration behavior for this scene.
- **SceneLaunchBehavior**: The launch behavior for a scene.
- **SceneRestorationBehavior**: The restoration behavior for a scene.
- **persistentSystemOverlays(_:)**: Sets the preferred visibility of the non-transient system views overlaying the app.
- **windowToolbarFullScreenVisibility(_:)**: Configures the visibility of the window toolbar when the window enters full screen mode.
- **WindowToolbarFullScreenVisibility**: The visibility of the window toolbar with respect to full screen mode.

## Managing window behavior

- **WindowManagerRole**: Options for defining how a scene’s windows behave when used within a managed window context, such as full screen mode and Stage Manager.
- **windowManagerRole(_:)**: Configures the role for windows derived from `self` when participating in a managed window context, such as full screen or Stage Manager.
- **WindowInteractionBehavior**: Options for enabling and disabling window interaction behaviors.
- **windowDismissBehavior(_:)**: Configures the dismiss functionality for the window enclosing `self`.
- **windowFullScreenBehavior(_:)**: Configures the full screen functionality for the window enclosing `self`.
- **windowMinimizeBehavior(_:)**: Configures the minimize functionality for the window enclosing `self`.
- **windowResizeBehavior(_:)**: Configures the resize functionality for the window enclosing `self`.
- **windowBackgroundDragBehavior(_:)**: Configures the behavior of dragging a window by its background.

## Interacting with volumes

- **onVolumeViewpointChange(updateStrategy:initial:_:)**: Adds an action to perform when the viewpoint of the volume changes.
- **supportedVolumeViewpoints(_:)**: Specifies which viewpoints are supported for the window bar and ornaments in a volume.
- **VolumeViewpointUpdateStrategy**: A type describing when the action provided to [onVolumeViewpointChange(updateStrategy:initial:_:)](View/onVolumeViewpointChange_updateStrategy_initial.zh-Hans.md) should be called.
- **Viewpoint3D**: A type describing what direction something is being viewed from.
- **SquareAzimuth**: A type describing what direction something is being viewed from along the horizontal plane and snapped to 4 directions.
- **WorldAlignmentBehavior**: A type representing the world alignment behavior for a scene.
- **volumeWorldAlignment(_:)**: Specifies how a volume should be aligned when moved in the world.
- **WorldScalingBehavior**: Specifies the scaling behavior a window should have within the world.
- **defaultWorldScaling(_:)**: Specify the world scaling behavior for the window.
- **WorldScalingCompensation**: Indicates whether returned metrics will take dynamic scaling into account.
- **worldTrackingLimitations**: The current limitations of the device tracking the user’s surroundings.
- **WorldTrackingLimitation**: A structure to represent limitations of tracking the user’s surroundings.
- **SurfaceSnappingInfo**: A type representing information about the window scenes snap state.

## Deprecated Types

- **ControlActiveState**: The active appearance expected of controls in a window.

## App structure

- **App organization**: Define the entry point and top-level structure of your app.
- **Scenes**: Declare the user interface groupings that make up the parts of your app.
- **Immersive spaces**: Display unbounded content in a person’s surroundings.
- **Documents**: Enable people to open and manage documents.
- **Navigation**: Enable people to move between different parts of your app’s view hierarchy within a scene.
- **Modal presentations**: Present content in a separate view that offers focused interaction.
- **Toolbars**: Provide immediate access to frequently used commands and controls.
- **Search**: Enable people to search for text or other content within your app.
- **App extensions**: Extend your app’s basic functionality to other parts of the system, like by adding a Widget.

