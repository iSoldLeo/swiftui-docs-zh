--- 来源：https://developer.apple.com/documentation/swiftui/scene
抓取时间：2025-12-04T13:47:23Z

---

# 场景

**Protocol**

应用用户界面的一部分，其生命周期由系统管理。

## 声明

```swift
@MainActor @preconcurrency protocol Scene
```

## 概述

您可以通过在应用的 [body-swift.property](App/body-swift_property.zh-Hans.md) 中组合一个或多个符合 `Scene` 协议的实例来创建 [App](App.zh-Hans.md)。您可以使用 SwiftUI 提供的内置场景（例如 [WindowGroup](WindowGroup.zh-Hans.md)），以及由其他场景组合而成的自定义场景。要创建自定义场景，请声明一个符合 `Scene` 协议的类型。实现所需的 [body-swift.property](scene/body-swift_property.zh-Hans.md) 计算属性，并提供自定义场景的内容：

```swift
struct MyScene: Scene {
    var body: some Scene {
        WindowGroup {
            MyRootView()
        }
    }
}
```

场景充当要向用户显示的视图层级的容器。系统会根据平台特性和应用程序的当前状态，决定何时以及如何以适合平台的方式在用户界面中呈现视图层级。例如，对于上面显示的窗口组，系统允许用户在 macOS 和 iPadOS 等平台上创建或删除包含 `MyRootView` 的窗口。在其他平台上，相同的视图层级在激活时可能会占据整个屏幕。

从场景或其某个视图中读取 [scenePhase](EnvironmentValues/scenePhase.zh-Hans.md) 环境值，以检查场景是否处于活动状态或其他状态。您可以使用 [Environment](Environment.zh-Hans.md) 属性创建一个包含场景阶段的属性，该阶段是 [ScenePhase](ScenePhase.zh-Hans.md) 枚举中的一个值：

```swift
struct MyScene: Scene {
    @Environment(\.scenePhase) private var scenePhase

    // ...
}
```

`Scene` 协议提供场景修改器，这些修改器定义为具有默认实现的协议方法，可用于配置场景。例如，您可以使用 [onChange(of:perform:)](scene/onChange_of_perform.zh-Hans.md) 修改器在值更改时触发操作。以下代码会在窗口组中的所有场景都移至后台时清空缓存：

```swift
struct MyScene: Scene {
    @Environment(\.scenePhase) private var scenePhase
    @StateObject private var cache = DataCache()

    var body: some Scene {
        WindowGroup {
            MyRootView()
        }
        .onChange(of: scenePhase) { newScenePhase in
            if newScenePhase == .background {
                cache.empty()
            }
        }
    }
}
```

如果类型的基本声明中包含符合性声明，则符合此协议的类型会继承协议的隔离性：`@preconcurrency @MainActor`

```swift
struct MyCustomType: Transition {
    // `@preconcurrency @MainActor` isolation by default
}
```

默认情况下，隔离到主 Actor，但这不是必需的。要在扩展中声明符合性声明以选择退出主 Actor 隔离：

```swift
extension MyCustomType: Transition {
    // `nonisolated` by default
}
```

## 创建场景

- **body**：场景的内容和行为。

- **Body**：表示此场景主体的场景类型。

## 监听更改

- **onChange(of:initial:_:)**：添加在给定值更改时要执行的操作。

- **handlesExternalEvents(matching:)**：指定 SwiftUI 为哪些外部事件打开已修改场景的新实例。

## 创建后台任务

- **backgroundTask(_:action:)**：当系统提供后台任务时，运行指定的操作。

## 管理应用存储

- **defaultAppStorage(_:)**：场景及其视图内容中使用的默认存储。

## 设置命令

- **commands(content:)**：向场景添加命令。

- **commandsRemoved()**：移除已修改场景中定义的所有命令。

- **commandsReplaced(content:)**：将已修改场景中定义的所有命令替换为构建器中的命令。

- **keyboardShortcut(_:)**：定义用于打开新场景窗口的键盘快捷键。

- **keyboardShortcut(_:modifiers:localization:)**：定义用于打开新场景窗口的键盘快捷键。

## 场景大小和位置

- **defaultPosition(_:)**：设置窗口的默认位置。

- **defaultSize(_:)**：设置窗口的默认大小。

- **defaultSize(width:height:)**：设置窗口的默认宽度和高度。

- **defaultSize(width:height:depth:)**：设置体素窗口的默认大小。

- **defaultSize(_:in:)**：设置体素窗口的默认大小。

- **defaultSize(width:height:depth:in:)**：设置体素窗口的默认大小。

- **defaultWindowPlacement(_:)**：定义用于确定窗口默认位置的函数。

- **windowResizability(_:)**：设置窗口的可调整大小方式。

- **windowIdealSize(_:)**：指定从此场景派生的窗口在缩放时如何确定其大小。

- **windowIdealPlacement(_:)**：提供一个函数，用于确定场景窗口缩放时的位置。

- **windowManagerRole(_:)**：配置从 `self` 派生的窗口在参与受管窗口上下文（例如全屏或舞台管理器）时的角色。

## 与体积交互

- **volumeWorldAlignment(_:)**：指定体积在世界中移动时应如何对齐。

- **defaultWorldScaling(_:)**：指定窗口的世界缩放行为。

## 配置场景可见性

- **defaultLaunchBehavior(_:)**：设置此场景的默认启动行为。

- **restorationBehavior(_:)**：设置此场景的恢复行为。

- **persistentSystemOverlays(_:)**：设置覆盖在应用程序上的非瞬态系统视图的首选可见性。

## 设置场景样式

- **immersionStyle(selection:in:)**：设置沉浸式空间的样式。

- **upperLimbVisibility(_:)**：设置呈现 [ImmersiveSpace](ImmersiveSpace.zh-Hans.md) 场景时用户上肢的首选可见性。

- **windowStyle(_:)**：设置此场景创建的窗口的样式。

- **windowLevel(_:)**：设置此场景的窗口级别。

- **windowToolbarStyle(_:)**：设置此场景中定义的工具栏的样式。

- **windowToolbarLabelStyle(_:)**：设置工具栏中项目的标签样式，并允许用户自定义。

- **windowToolbarLabelStyle(fixed:)**：设置工具栏中项目的标签样式。

## 配置数据模型

- **modelContext(_:)**：设置此场景环境中的模型上下文。

- **modelContainer(_:)**：设置此场景环境中的模型容器及其关联的模型上下文。

- **modelContainer(for:inMemory:isAutosaveEnabled:isUndoEnabled:onSetup:)**：设置此场景中用于存储所提供模型类型的模型容器（如有必要，将创建新容器），并为该容器设置此场景环境中的模型上下文。

## 管理环境

- **environment(_:)**：将可观察对象放置在场景环境中。

- **environment(_:_:)**：将指定键路径的环境值设置为给定值。

- **environmentObject(_:)**：向视图子层次结构提供 `ObservableObject`。

- **transformEnvironment(_:transform:)**：使用给定函数转换指定键路径的环境值。

## 与对话框交互

- **dialogIcon(_:)**：配置警报使用的图标。

- **dialogSeverity(_:)**：设置警报的严重性。

- **dialogSuppressionToggle(isSuppressed:)**：允许用户使用自定义抑制消息抑制警报。

- **dialogSuppressionToggle(_:isSuppressed:)**：允许用户使用自定义抑制消息来抑制警报。

## 支持拖拽行为

- **windowBackgroundDragBehavior(_:)**：配置拖动窗口背景的行为。

## 已弃用符号

- **onChange(of:perform:)**：添加在给定值更改时要执行的操作。

## 实例方法

- **documentBrowserContextMenu(_:)**：向 `DocumentGroupLaunchScene` 添加接受选定文件列表作为参数的操作。

- **immersiveContentBrightness(_:)**：设置沉浸式空间的内容亮度。

- **immersiveEnvironmentBehavior(_:)**：设置打开此场景时应应用的沉浸式环境行为。

- **menuBarExtraStyle(_:)**：设置此场景创建的菜单栏附加组件的样式。

## 创建场景

- **SceneBuilder**：用于将多个场景组合成一个复合场景的结果构建器。

## 符合规范的类型

- AlertScene

- AssistiveAccess

- DocumentGroup

- DocumentGroupLaunchScene

- Group

- ImmersiveSpace

- MenuBarExtra

- ModifiedContent

- RemoteImmersiveSpace

- Settings

- UtilityWindow

- WKNotificationScene

- Window

- WindowGroup


---
source: https://developer.apple.com/documentation/swiftui/scene
crawled: 2025-12-04T13:47:23Z
---

# Scene

**Protocol**

A part of an app’s user interface with a life cycle managed by the system.

## Declaration

```swift
@MainActor @preconcurrency protocol Scene
```

## Overview

You create an [App](App.zh-Hans.md) by combining one or more instances that conform to the `Scene` protocol in the app’s [body-swift.property](App/body-swift_property.zh-Hans.md). You can use the built-in scenes that SwiftUI provides, like [WindowGroup](WindowGroup.zh-Hans.md), along with custom scenes that you compose from other scenes. To create a custom scene, declare a type that conforms to the `Scene` protocol. Implement the required [body-swift.property](scene/body-swift_property.zh-Hans.md) computed property and provide the content for your custom scene:

```swift
struct MyScene: Scene {
    var body: some Scene {
        WindowGroup {
            MyRootView()
        }
    }
}
```

A scene acts as a container for a view hierarchy that you want to display to the user. The system decides when and how to present the view hierarchy in the user interface in a way that’s platform-appropriate and dependent on the current state of the app. For example, for the window group shown above, the system lets the user create or remove windows that contain `MyRootView` on platforms like macOS and iPadOS. On other platforms, the same view hierarchy might consume the entire display when active.

Read the [scenePhase](EnvironmentValues/scenePhase.zh-Hans.md) environment value from within a scene or one of its views to check whether a scene is active or in some other state. You can create a property that contains the scene phase, which is one of the values in the [ScenePhase](ScenePhase.zh-Hans.md) enumeration, using the [Environment](Environment.zh-Hans.md) attribute:

```swift
struct MyScene: Scene {
    @Environment(\.scenePhase) private var scenePhase

    // ...
}
```

The `Scene` protocol provides scene modifiers, defined as protocol methods with default implementations, that you use to configure a scene. For example, you can use the [onChange(of:perform:)](scene/onChange_of_perform.zh-Hans.md) modifier to trigger an action when a value changes. The following code empties a cache when all of the scenes in the window group have moved to the background:

```swift
struct MyScene: Scene {
    @Environment(\.scenePhase) private var scenePhase
    @StateObject private var cache = DataCache()

    var body: some Scene {
        WindowGroup {
            MyRootView()
        }
        .onChange(of: scenePhase) { newScenePhase in
            if newScenePhase == .background {
                cache.empty()
            }
        }
    }
}
```

A type conforming to this protocol inherits `@preconcurrency @MainActor` isolation from the protocol if the conformance is included in the type’s base declaration:

```swift
struct MyCustomType: Transition {
    // `@preconcurrency @MainActor` isolation by default
}
```

Isolation to the main actor is the default, but it’s not required. Declare the conformance in an extension to opt out of main actor isolation:

```swift
extension MyCustomType: Transition {
    // `nonisolated` by default
}
```

## Creating a scene

- **body**: The content and behavior of the scene.
- **Body**: The type of scene that represents the body of this scene.

## Watching for changes

- **onChange(of:initial:_:)**: Adds an action to perform when the given value changes.
- **handlesExternalEvents(matching:)**: Specifies the external events for which SwiftUI opens a new instance of the modified scene.

## Creating background tasks

- **backgroundTask(_:action:)**: Runs the specified action when the system provides a background task.

## Managing app storage

- **defaultAppStorage(_:)**: The default store used by `AppStorage` contained within the scene and its view content.

## Setting commands

- **commands(content:)**: Adds commands to the scene.
- **commandsRemoved()**: Removes all commands defined by the modified scene.
- **commandsReplaced(content:)**: Replaces all commands defined by the modified scene with the commands from the builder.
- **keyboardShortcut(_:)**: Defines a keyboard shortcut for opening new scene windows.
- **keyboardShortcut(_:modifiers:localization:)**: Defines a keyboard shortcut for opening new scene windows.

## Sizing and positioning the scene

- **defaultPosition(_:)**: Sets a default position for a window.
- **defaultSize(_:)**: Sets a default size for a window.
- **defaultSize(width:height:)**: Sets a default width and height for a window.
- **defaultSize(width:height:depth:)**: Sets a default size for a volumetric window.
- **defaultSize(_:in:)**: Sets a default size for a volumetric window.
- **defaultSize(width:height:depth:in:)**: Sets a default size for a volumetric window.
- **defaultWindowPlacement(_:)**: Defines a function used for determining the default placement of windows.
- **windowResizability(_:)**: Sets the kind of resizability to use for a window.
- **windowIdealSize(_:)**: Specifies how windows derived form this scene should determine their size when zooming.
- **windowIdealPlacement(_:)**: Provides a function which determines a placement to use when windows of a scene zoom.
- **windowManagerRole(_:)**: Configures the role for windows derived from `self` when participating in a managed window context, such as full screen or Stage Manager.

## Interacting with volumes

- **volumeWorldAlignment(_:)**: Specifies how a volume should be aligned when moved in the world.
- **defaultWorldScaling(_:)**: Specify the world scaling behavior for the window.

## Configuring scene visibility

- **defaultLaunchBehavior(_:)**: Sets the default launch behavior for this scene.
- **restorationBehavior(_:)**: Sets the restoration behavior for this scene.
- **persistentSystemOverlays(_:)**: Sets the preferred visibility of the non-transient system views overlaying the app.

## Styling the scene

- **immersionStyle(selection:in:)**: Sets the style for an immersive space.
- **upperLimbVisibility(_:)**: Sets the preferred visibility of the user’s upper limbs, while an [ImmersiveSpace](ImmersiveSpace.zh-Hans.md) scene is presented.
- **windowStyle(_:)**: Sets the style for windows created by this scene.
- **windowLevel(_:)**: Sets the window level of this scene.
- **windowToolbarStyle(_:)**: Sets the style for the toolbar defined within this scene.
- **windowToolbarLabelStyle(_:)**: Sets the label style of items in a toolbar and enables user customization.
- **windowToolbarLabelStyle(fixed:)**: Sets the label style of items in a toolbar.

## Configuring a data model

- **modelContext(_:)**: Sets the model context in this scene’s environment.
- **modelContainer(_:)**: Sets the model container and associated model context in this scene’s environment.
- **modelContainer(for:inMemory:isAutosaveEnabled:isUndoEnabled:onSetup:)**: Sets the model container in this scene for storing the provided model type, creating a new container if necessary, and also sets a model context for that container in this scene’s environment.

## Managing the environment

- **environment(_:)**: Places an observable object in the scene’s environment.
- **environment(_:_:)**: Sets the environment value of the specified key path to the given value.
- **environmentObject(_:)**: Supplies an `ObservableObject` to a view subhierarchy.
- **transformEnvironment(_:transform:)**: Transforms the environment value of the specified key path with the given function.

## Interacting with dialogs

- **dialogIcon(_:)**: Configures the icon used by alerts.
- **dialogSeverity(_:)**: Sets the severity for alerts.
- **dialogSuppressionToggle(isSuppressed:)**: Enables user suppression of an alert with a custom suppression message.
- **dialogSuppressionToggle(_:isSuppressed:)**: Enables user suppression of an alert with a custom suppression message.

## Supporting drag behavior

- **windowBackgroundDragBehavior(_:)**: Configures the behavior of dragging a window by its background.

## Deprecated symbols

- **onChange(of:perform:)**: Adds an action to perform when the given value changes.

## Instance Methods

- **documentBrowserContextMenu(_:)**: Adds to a `DocumentGroupLaunchScene` actions that accept a list of selected files as their parameter.
- **immersiveContentBrightness(_:)**: Sets the content brightness of an immersive space.
- **immersiveEnvironmentBehavior(_:)**: Sets the immersive environment behavior that should apply when this scene opens.
- **menuBarExtraStyle(_:)**: Sets the style for menu bar extra created by this scene.

## Creating scenes

- **SceneBuilder**: A result builder for composing a collection of scenes into a single composite scene.

## Conforming Types

- AlertScene
- AssistiveAccess
- DocumentGroup
- DocumentGroupLaunchScene
- Group
- ImmersiveSpace
- MenuBarExtra
- ModifiedContent
- RemoteImmersiveSpace
- Settings
- UtilityWindow
- WKNotificationScene
- Window
- WindowGroup

