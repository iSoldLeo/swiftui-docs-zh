--- 来源：https://developer.apple.com/documentation/SwiftUI/Customizing-window-styles-and-state-restoration-behavior-in-macOS

抓取时间：2025-12-02T15:51:07Z

---

# macOS 中的自定义窗口样式和状态恢复行为 | Apple 开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ Windows ](/documentation/swiftui/windows)

- [ 自定义 macOS 中的窗口样式和状态恢复行为 ](/documentation/SwiftUI/Customizing-window-styles-and-state-restoration-behavior-in-macOS)

- [ Windows ](/documentation/swiftui/windows)

- 自定义 macOS 中的窗口样式和状态恢复行为

示例代码# 自定义 macOS 中的窗口样式和状态恢复行为

配置您的应用窗口在 macOS 中的外观和功能，以提供更具吸引力和一致性的体验。[ 下载 (1.2 GB) ](https://docs-assets.developer.apple.com/published/08bd3c5ea0b3/DestinationVideo.zip)macOS 15.0+## [概述](/documentation/SwiftUI/Customizing-window-styles-and-state-restoration-behavior-in-macOS#overview)

macOS 目标 [目标平台]视频](/documentation/visionOS/destination-video)演示了如何利用窗口和场景自定义 API（macOS 15 及更高版本可用）来定制 macOS 中的应用体验。这包括更改工具栏的外观和可见性、扩展窗口的拖动区域、参与窗口的缩放操作以及修改窗口的状态恢复行为。

## [移除窗口工具栏的标题和背景](/documentation/SwiftUI/Customizing-window-styles-and-state-restoration-behavior-in-macOS#Remove-the-title-and-background-from-the-windows-toolbar)

Destination Video 使用标签页视图作为其主要用户界面组件，在 macOS 中，它类似于双列导航分割视图。在这种配置中，每个标签页都作为侧边栏中的一个条目显示，并参与应用的导航。由于侧边栏可以直观地指示您在导航层级中的位置，并且应用的内容不需要任何额外的工具栏项目，因此无需工具栏。移除工具栏可以提升底层内容的显示效果，使其延伸至窗口边缘。

要移除工具栏的背景，`ContentView` 调用 [`toolbarBackgroundVisibility(_:for:)`](/documentation/swiftui/view/toolbarbackgroundvisibility(_:for:)) 视图方法：

```
.toolbarBackgroundVisibility(.hidden, for: .windowToolbar)

```

然后移除工具栏的标题：

```
.toolbar(removing: .title)

```

在这种情况下，应用程序仍然需要窗口控制按钮来关闭或最小化窗口，或进入全屏模式，因此它使用单独的视图方法仅移除标题和工具栏背景。要完全移除工具栏，请改用 [`toolbarVisibility(_:for:)`](/documentation/swiftui/view/toolbarvisibility(_:for:)) 视图方法。

带有工具栏背景和标题的窗口

移除工具栏背景和标题后的窗口

需要注意的是，这些只是视觉上的变化。系统会继续向屏幕阅读器等辅助工具提供窗口标题，并且当窗口打开时，应用程序的“窗口”菜单也会继续显示该标题。

## [扩展窗口拖动区域](/documentation/SwiftUI/Customizing-window-styles-and-state-restoration-behavior-in-macOS#Extend-the-windows-drag-region)

在 macOS 中，通常情况下，移动窗口需要拖动窗口的工具栏。但是，如果您选择移除工具栏的背景或完全隐藏工具栏，请使用 [`WindowDragGesture`](/documentation/swiftui/windowdraggesture) 扩展窗口的拖动区域，以确保窗口仍然可以拖动。

Destination Video 的 `PlayerView` 将此手势添加到透明叠加层中，并将该叠加层插入视频内容和播放控件之间。这样，您就可以安全地拖动窗口，而不会干扰 AVKit 提供的系统播放界面。

```
.gesture(WindowDragGesture())

```

播放器还使用 [`allowsWindowActivationEvents(_:)`](/documentation/swiftui/view/allowswindowactivationevents(_:)) 视图方法，使已安装的窗口拖动手势能够接收激活窗口的事件——例如，如果窗口位于后台，您点击它并立即拖动。

```
.allowsWindowActivationEvents(true)

```

## [自定义窗口缩放行为](/documentation/SwiftUI/Customizing-window-styles-and-state-restoration-behavior-in-macOS#Customize-the-windows-zoom-behavior)

默认情况下，窗口工具栏提供用于关闭窗口、最小化窗口和进入全屏模式的按钮。如果您按住 Option 键并单击绿色按钮，窗口将缩放而不是进入全屏模式。

通常，窗口会缩放到其定义的最大尺寸，或显示器允许的最大尺寸。不过，您可以使用 [`windowIdealPlacement(_:)`](/documentation/swiftui/scene/windowidealplacement(_:)) 场景方法来覆盖此默认行为，并提供更适合窗口内容的尺寸和位置。应用程序使用此方法为视频播放器设置最大尺寸，以保持视频的宽高比，防止视频上下方出现黑边。

```
.windowIdealPlacement { proxy, context in
    let displayBounds = context.defaultDisplay.visibleRect
    let idealSize = proxy.sizeThatFits(.unspecified)
    
    // Calculate the content's aspect ratio.
    let aspectRatio = aspectRatio(of: idealSize)
    // Determine the deltas between the display's size and the content's size.
    let deltas = deltas(of: displayBounds.size, idealSize)
    
    // Calculate the window's zoomed size while maintaining the aspect ratio
    // of the content.
    let size = calculateZoomedSize(
        of: idealSize,
        inBounds: displayBounds,
        withAspectRatio: aspectRatio,
        andDeltas: deltas
    )
    
    // Position the window in the center of the display and return the
    // corresponding window placement.
    let position = position(of: size, centeredIn: displayBounds)
    return WindowPlacement(position, size: size)
}

```

此实现还确保缩放后的窗口在缩放时始终位于屏幕中心。

## [修改窗口参与状态恢复的方式](/documentation/SwiftUI/Customizing-window-styles-and-state-restoration-behavior-in-macOS#Modify-how-the-window-participates-in-state-restoration)

在 macOS 中，状态恢复是可选的，用户可以在系统设置中启用（或禁用）它。默认情况下，您的 SwiftUI 应用程序会遵循此设置，但您可以选择覆盖它，并为应用程序的每个窗口指定首选的恢复行为。例如，对于代表短暂活动的窗口，或者从先前会话恢复底层状态较为困难或成本较高的情况，您可能希望禁用状态恢复。

在 macOS 系统中运行时，Destination Video 使用 [`SceneRestorationBehavior`](/documentation/swiftui/scenerestorationbehavior) 视图修饰符来禁用视频播放器视图的状态恢复。

```
.restorationBehavior(.disabled)

```

由于该应用的视频时长较短，用户与视频的交互也较为短暂，因此在下次启动时恢复视频播放器状态是没有意义的。

## [另请参阅](/documentation/SwiftUI/Customizing-window-styles-and-state-restoration-behavior-in-macOS#See-Also)

#### [相关示例](/documentation/SwiftUI/Customizing-window-styles-and-state-restoration-behavior-in-macOS#Related-samples)

[目标视频](/documentation/visionOS/destination-video)#### [相关视频](/documentation/SwiftUI/Customizing-window-styles-and-state-restoration-behavior-in-macOS#Related-videos)

[使用 SwiftUI 定制 macOS 窗口](https://developer.apple.com/videos/play/wwdc2024/10148)## [另请参阅](/documentation/SwiftUI/Customizing-window-styles-and-state-restoration-behavior-in-macOS#see-also)

### [基础知识](/documentation/SwiftUI/Customizing-window-styles-and-state-restoration-behavior-in-macOS#Essentials)

[为您的 SwiftUI 应用添加多个窗口](/documentation/swiftui/bringing-multiple-windows-to-your-swiftui-app)通过响应状态变化来构建丰富的视图，并自定义 iPadOS 和 macOS 上应用的场景呈现和行为。

---
source: https://developer.apple.com/documentation/SwiftUI/Customizing-window-styles-and-state-restoration-behavior-in-macOS
crawled: 2025-12-02T15:51:07Z
---

# Customizing window styles and state-restoration behavior in macOS | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ Windows ](/documentation/swiftui/windows)

- [ Customizing window styles and state-restoration behavior in macOS ](/documentation/SwiftUI/Customizing-window-styles-and-state-restoration-behavior-in-macOS)

- [ Windows ](/documentation/swiftui/windows)

-  Customizing window styles and state-restoration behavior in macOS 

Sample Code# Customizing window styles and state-restoration behavior in macOS

Configure how your app’s windows look and function in macOS to provide an engaging and more coherent experience.[ Download (1.2 GB) ](https://docs-assets.developer.apple.com/published/08bd3c5ea0b3/DestinationVideo.zip)macOS 15.0+## [Overview](/documentation/SwiftUI/Customizing-window-styles-and-state-restoration-behavior-in-macOS#overview)

The macOS target of [Destination Video](/documentation/visionOS/destination-video) demonstrates how you can leverage the window and scene customization APIs (available in macOS 15 and later) to tailor an app’s experience in macOS. This includes changing a toolbar’s appearance and visibility, extending a window’s drag region, participating in a window’s zoom action, and modifying a window’s state restoration behavior.

## [Remove the title and background from the window’s toolbar](/documentation/SwiftUI/Customizing-window-styles-and-state-restoration-behavior-in-macOS#Remove-the-title-and-background-from-the-windows-toolbar)

Destination Video uses a tab view as its main user interface component, and in macOS, this appears similar to a two-column navigation split view. In this configuration, each tab appears as an entry in the sidebar and participates in the app’s navigation. Because the sidebar provides a visual indication of where you are in that navigation hierarchy, and the app’s content doesn’t require any additional toolbar items, a toolbar isn’t necessary. Removing the toolbar can elevate the underlying content by letting it extend right up to the window’s edge.

To remove the toolbar’s background, `ContentView` calls the [`toolbarBackgroundVisibility(_:for:)`](/documentation/swiftui/view/toolbarbackgroundvisibility(_:for:)) view method:



```
.toolbarBackgroundVisibility(.hidden, for: .windowToolbar)

```

And then removes the toolbar’s title:



```
.toolbar(removing: .title)

```

In this instance, the app still requires the window control buttons to close or minimize the window or enter full-screen mode, so it uses individual view methods to remove only the title and bar background. To remove the toolbar entirely, use the [`toolbarVisibility(_:for:)`](/documentation/swiftui/view/toolbarvisibility(_:for:)) view method instead.

A window with a toolbar background and title

A window with the toolbar background and title removed

It’s important to note that these are visual changes only. The system continues to provide the window’s title to accessibility tools such as screen readers, and the app’s Window menu continues to show the title while the window is open.

## [Extend the window’s drag region](/documentation/SwiftUI/Customizing-window-styles-and-state-restoration-behavior-in-macOS#Extend-the-windows-drag-region)

To move a window in macOS, you typically drag that window’s toolbar. However, if you choose to remove the background from a toolbar, or hide the toolbar completely, use [`WindowDragGesture`](/documentation/swiftui/windowdraggesture) to extend that window’s drag region and make sure the window is still draggable.

Destination Video’s `PlayerView` adds this gesture to a transparent overlay and inserts the overlay between the video content and the playback controls. This enables you to safely drag the window and not interfere with the system playback UI that AVKit provides.



```
.gesture(WindowDragGesture())

```

The player also uses the [`allowsWindowActivationEvents(_:)`](/documentation/swiftui/view/allowswindowactivationevents(_:)) view method to enable the installed window drag gesture to receive events that activate the window — for example, if the window is in the background and you click it and immediately drag.



```
.allowsWindowActivationEvents(true)

```

## [Customize the window’s zoom behavior](/documentation/SwiftUI/Customizing-window-styles-and-state-restoration-behavior-in-macOS#Customize-the-windows-zoom-behavior)

By default, a window’s toolbar provides buttons that close the window, minimize the window, and enter full-screen mode. If you press and hold the Option key and click the green button, the window zooms instead of going full screen.

Typically, a window zooms to either its defined maximum size, or as large as the display permits. However, you can use the [`windowIdealPlacement(_:)`](/documentation/swiftui/scene/windowidealplacement(_:)) scene method to override this behavior and provide a size and position that’s more appropriate for the window’s contents. The app uses this method to provide a maximum size for the video player that maintains the video’s aspect ratio to prevent black bars appearing above and below it.



```
.windowIdealPlacement { proxy, context in
    let displayBounds = context.defaultDisplay.visibleRect
    let idealSize = proxy.sizeThatFits(.unspecified)
    
    // Calculate the content's aspect ratio.
    let aspectRatio = aspectRatio(of: idealSize)
    // Determine the deltas between the display's size and the content's size.
    let deltas = deltas(of: displayBounds.size, idealSize)
    
    // Calculate the window's zoomed size while maintaining the aspect ratio
    // of the content.
    let size = calculateZoomedSize(
        of: idealSize,
        inBounds: displayBounds,
        withAspectRatio: aspectRatio,
        andDeltas: deltas
    )
    
    // Position the window in the center of the display and return the
    // corresponding window placement.
    let position = position(of: size, centeredIn: displayBounds)
    return WindowPlacement(position, size: size)
}

```

This implementation also ensures the zoomed window appears in the center of the display while zooming.

## [Modify how the window participates in state restoration](/documentation/SwiftUI/Customizing-window-styles-and-state-restoration-behavior-in-macOS#Modify-how-the-window-participates-in-state-restoration)

In macOS, state restoration is optional and a person enables (or disables) it systemwide in System Settings. By default, your SwiftUI app respects this setting, but you can choose to override it and specify the preferred restoration behavior for each of your app’s windows. For example, you may want to opt out of state restoration for a window that represents a transient activity, or where it’s difficult or expensive to restore the underlying state from a previous session.

When running in macOS, Destination Video uses the [`SceneRestorationBehavior`](/documentation/swiftui/scenerestorationbehavior) view modifier to disable state restoration for the video player view.



```
.restorationBehavior(.disabled)

```

As the app’s videos are brief, and a person’s interactions with them are short-lived, it doesn’t make sense to restore the video player on the next launch.

## [See Also](/documentation/SwiftUI/Customizing-window-styles-and-state-restoration-behavior-in-macOS#See-Also)

#### [Related samples](/documentation/SwiftUI/Customizing-window-styles-and-state-restoration-behavior-in-macOS#Related-samples)

[ Destination Video ](/documentation/visionOS/destination-video)#### [Related videos](/documentation/SwiftUI/Customizing-window-styles-and-state-restoration-behavior-in-macOS#Related-videos)

[ Tailor macOS windows with SwiftUI ](https://developer.apple.com/videos/play/wwdc2024/10148)## [See Also](/documentation/SwiftUI/Customizing-window-styles-and-state-restoration-behavior-in-macOS#see-also)

### [Essentials](/documentation/SwiftUI/Customizing-window-styles-and-state-restoration-behavior-in-macOS#Essentials)

[Bringing multiple windows to your SwiftUI app](/documentation/swiftui/bringing-multiple-windows-to-your-swiftui-app)Compose rich views by reacting to state changes and customize your app’s scene presentation and behavior on iPadOS and macOS.