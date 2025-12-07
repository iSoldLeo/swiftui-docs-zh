--- 来源：https://developer.apple.com/documentation/SwiftUI/RemoteImmersiveSpace

抓取时间：2025-12-02T17:22:02Z

---

# RemoteImmersiveSpace

**Structure**

一个将内容呈现在远程设备上的无限空间中的场景。

## 声明

```swift
struct RemoteImmersiveSpace<Content, Data> where Content : ImmersiveSpaceContent, Data : Decodable, Data : Encodable, Data : Hashable
```

## 概述

使用远程沉浸式空间作为容器，用于存放 macOS 应用在用户选择的 VisionOS 设备上呈现的合成器内容。您声明为远程沉浸式空间内容的合成器内容将作为其模板：

```swift
@main
struct SolarSystemApp: App {
    var body: some Scene {
        RemoteImmersiveSpace {
            CompositorLayer { layerRenderer in
                // Set up and run the Metal render loop.
                let renderThread = Thread {
                    let engine = solar_engine_create(layerRenderer)
                    solar_engine_render_loop(engine)
                }
                renderThread.name = "Render Thread"
                renderThread.start()
            }
        }
    }
}
```

### 使用环境、状态和修饰符

声明符合 [CompositorContent](CompositorContent.zh-Hans.md) 协议的类型以访问环境，声明 `@State` 变量，并在远程沉浸式空间中使用修饰符。

```swift
struct SolarSystem: CompositorContent {
    @Environment(\.scenePhase) private var scenePhase
    @State private var model: AppModel

    var body: some CompositorContent {
        CompositorLayer { layerRenderer in
            // Set up and run the Metal render loop.
            let renderThread = Thread {
                let engine = solar_engine_create(layerRenderer)
                solar_engine_render_loop(engine)
            }
            renderThread.name = "Render Thread"
            renderThread.start()
        }
        .onChange(of: scenePhase) {
            model.remoteSpaceActive = scenePhase == .active
        }
    }
}
```

### 识别远程设备

使用 [remoteDeviceIdentifier](EnvironmentValues/remoteDeviceIdentifier.zh-Hans.md) 环境值来识别场景运行的设备。此标识符也可用于初始化与远程设备关联的 `ARKitSession`。

```swift
struct SolarSystem: CompositorContent {
    @Environment(\.remoteDeviceIdentifier) private var deviceID

    var body: some CompositorContent {
        CompositorLayer { layerRenderer in
            // Create an ARSession for the device
            let arSession = ARKitSession(deviceID)

            // Set up and run the Metal render loop.
            let renderThread = Thread {
                let engine = solar_engine_create(
                    layerRenderer, arSession)
                solar_engine_render_loop(engine)
            }
            renderThread.name = "Render Thread"
            renderThread.start()
        }
    }
}
```

### 设置沉浸式空间样式

默认情况下，沉浸式空间使用 [mixed](ImmersionStyle/mixed.zh-Hans.md) 样式，将虚拟内容置于用户的周围环境中。您可以通过向场景添加 [immersionStyle(selection:in:)](Scene/immersionStyle_selection_in.zh-Hans.md) 场景修改器来选择不同的沉浸式空间样式。例如，您可以使用 [full](ImmersionStyle/full.zh-Hans.md) 沉浸式样式完全控制视觉体验：

```swift
@main
struct SolarSystemApp: App {
    @State private var style: ImmersionStyle = .full

    var body: some Scene {
        RemoteImmersiveSpace {
            SolarSystem()
        }
        .immersionStyle(selection: $style, in: .full)
    }
}
```

您可以在呈现沉浸式空间后，通过更改修改器的 `selection` 输入来更改沉浸式样式，但您只能使用在修改器的第二个参数中指定的值之一。

### 打开远程沉浸式空间

您可以通过为其指定标识符，以编程方式打开远程沉浸式空间。例如，您可以为上例中的太阳系视图添加标签：

```swift
RemoteImmersiveSpace(id: "solarSystem") {
    SolarSystem()
}
```

在代码的其他部分，您可以使用 [openImmersiveSpace](EnvironmentValues/openImmersiveSpace.zh-Hans.md) 环境值来获取给定 [Environment](Environment.zh-Hans.md) 对应的 [OpenImmersiveSpaceAction](OpenImmersiveSpaceAction.zh-Hans.md) 结构的实例。您可以直接调用该实例——例如，从按钮的闭包中调用，如下面的代码所示——使用标识符：

```swift
struct NewSolarSystemImmersiveSpaceButton: View {
    @Environment(\.openImmersiveSpace) private var openImmersiveSpace
    @Environment(\.supportsRemoteScenes) private var supportsRemoteScenes

    var body: some View {
        Button("Present Solar System") {
            Task {
                await openImmersiveSpace(id: "solarSystem")
            }
        }
        .disabled(!supportsRemoteScenes)
        .help(!supportsRemoteScenes
            ? "Presenting remote scenes is not supported on this device."
            : "")
    }
}
```

使用 `await` 标记对该操作的调用，因为它是异步执行的。当您的应用打开远程沉浸式空间时，系统可能会询问用户用于显示内容的首选设备。选择后，远程设备上的系统会隐藏所有其他可见的应用。系统一次只允许打开一个沉浸式空间。请务必在打开另一个沉浸式空间之前关闭当前打开的沉浸式空间。

### 关闭远程沉浸式空间

您可以通过调用环境中的 [dismissImmersiveSpace](EnvironmentValues/dismissImmersiveSpace.zh-Hans.md) 操作来关闭沉浸式空间。例如，您可以定义一个用于关闭沉浸式空间的按钮：

```swift
struct DismissImmersiveSpaceButton: View {
    @Environment(\.dismissImmersiveSpace)
    private var dismissImmersiveSpace

    var body: some View {
        Button("Close Solar System") {
            Task {
                await dismissImmersiveSpace()
            }
        }
    }
}
```

关闭操作与打开操作一样，都是异步运行的。关闭沉浸式空间时无需指定标识符，因为一次只能打开一个沉浸式空间。

### 启动时呈现沉浸式空间

应用启动时，会打开应用主体中列出的第一个场景的实例。启动时打开沉浸式空间时，系统可能仍会询问用户用于显示内容的首选设备。

## 初始化器

- **init(content:)**：创建远程沉浸式空间。

- **init(for:content:)**：为指定类型的数据创建远程沉浸式空间。

- **init(for:content:defaultValue:)**：为指定类型的数据创建远程沉浸式空间，如果未设置数据，则使用默认值。

- **init(id:content:)**：创建与指定标识符关联的远程沉浸式空间。

- **init(id:for:content:)**：为指定类型的数据创建与标识符关联的远程沉浸式空间。

- **init(id:for:content:defaultValue:)**：为指定类型的数据创建与标识符关联的远程沉浸式空间，如果未设置数据，则使用默认值。

## 处理远程沉浸式空间

- **RemoteDeviceIdentifier**：一种不透明类型，用于标识在 [RemoteImmersiveSpace](RemoteImmersiveSpace.zh-Hans.md) 中显示场景内容的远程设备。

## 符合以下规范

- 场景


---
source: https://developer.apple.com/documentation/SwiftUI/RemoteImmersiveSpace
crawled: 2025-12-02T17:22:02Z
---

# RemoteImmersiveSpace

**Structure**

A scene that presents its content in an unbounded space on a remote device.

## Declaration

```swift
struct RemoteImmersiveSpace<Content, Data> where Content : ImmersiveSpaceContent, Data : Decodable, Data : Encodable, Data : Hashable
```

## Overview

Use a remote immersive space as a container for compositor content that your macOS app presents on a user’s chosen visionOS device. The compositor content that you declare as the remote immersive space’s content serves as a template for it:

```swift
@main
struct SolarSystemApp: App {
    var body: some Scene {
        RemoteImmersiveSpace {
            CompositorLayer { layerRenderer in
                // Set up and run the Metal render loop.
                let renderThread = Thread {
                    let engine = solar_engine_create(layerRenderer)
                    solar_engine_render_loop(engine)
                }
                renderThread.name = "Render Thread"
                renderThread.start()
            }
        }
    }
}
```

### Using the environment, state, and modifiers

Declare types that conform to the [CompositorContent](CompositorContent.zh-Hans.md) protocol to access the environment, declare `@State` variables, and use modifiers inside your remote immersive space.

```swift
struct SolarSystem: CompositorContent {
    @Environment(\.scenePhase) private var scenePhase
    @State private var model: AppModel

    var body: some CompositorContent {
        CompositorLayer { layerRenderer in
            // Set up and run the Metal render loop.
            let renderThread = Thread {
                let engine = solar_engine_create(layerRenderer)
                solar_engine_render_loop(engine)
            }
            renderThread.name = "Render Thread"
            renderThread.start()
        }
        .onChange(of: scenePhase) {
            model.remoteSpaceActive = scenePhase == .active
        }
    }
}
```

### Identifying the remote device

Use the [remoteDeviceIdentifier](EnvironmentValues/remoteDeviceIdentifier.zh-Hans.md) environment value to identify the device the scene is running on. This identifier can also be used to initialize an `ARKitSession` associated with the remote device.

```swift
struct SolarSystem: CompositorContent {
    @Environment(\.remoteDeviceIdentifier) private var deviceID

    var body: some CompositorContent {
        CompositorLayer { layerRenderer in
            // Create an ARSession for the device
            let arSession = ARKitSession(deviceID)

            // Set up and run the Metal render loop.
            let renderThread = Thread {
                let engine = solar_engine_create(
                    layerRenderer, arSession)
                solar_engine_render_loop(engine)
            }
            renderThread.name = "Render Thread"
            renderThread.start()
        }
    }
}
```



### Style the immersive space

By default, immersive spaces use the [mixed](ImmersionStyle/mixed.zh-Hans.md) style which places virtual content in a person’s surroundings. You can select a different style for the immersive space by adding the [immersionStyle(selection:in:)](Scene/immersionStyle_selection_in.zh-Hans.md) scene modifier to the scene. For example, you can completely control the visual experience using the [full](ImmersionStyle/full.zh-Hans.md) immersion style:

```swift
@main
struct SolarSystemApp: App {
    @State private var style: ImmersionStyle = .full

    var body: some Scene {
        RemoteImmersiveSpace {
            SolarSystem()
        }
        .immersionStyle(selection: $style, in: .full)
    }
}
```

You can change the immersion style after presenting the immersive space by changing the modifier’s `selection` input, although you can only use one of the values that you specify in the modifier’s second parameter.

### Open a remote immersive space

You can programmatically open a remote immersive space by giving it an identifier. For example, you can label the solar system view from the previous example:

```swift
RemoteImmersiveSpace(id: "solarSystem") {
    SolarSystem()
}
```

Elsewhere in your code, you use the [openImmersiveSpace](EnvironmentValues/openImmersiveSpace.zh-Hans.md) environment value to get the instance of the [OpenImmersiveSpaceAction](OpenImmersiveSpaceAction.zh-Hans.md) structure for a given [Environment](Environment.zh-Hans.md). You call the instance directly — for example, from a button’s closure, like in the following code — using the identifier:

```swift
struct NewSolarSystemImmersiveSpaceButton: View {
    @Environment(\.openImmersiveSpace) private var openImmersiveSpace
    @Environment(\.supportsRemoteScenes) private var supportsRemoteScenes

    var body: some View {
        Button("Present Solar System") {
            Task {
                await openImmersiveSpace(id: "solarSystem")
            }
        }
        .disabled(!supportsRemoteScenes)
        .help(!supportsRemoteScenes
            ? "Presenting remote scenes is not supported on this device."
            : "")
    }
}
```

Mark the call to the action with `await` because it executes asynchronously. When your app opens a remote immersive space, the system may ask the user for a preferred device with which to display the content. Upon selection, the system on the remote device hides all other visible apps. The system allows only one immersive space to be open at a time. Be sure to close the open immersive space before opening another one.

### Dismiss a remote immersive space

You can dismiss an immersive space by calling the [dismissImmersiveSpace](EnvironmentValues/dismissImmersiveSpace.zh-Hans.md) action from the environment. For example, you can define a button that dismisses an immersive space:

```swift
struct DismissImmersiveSpaceButton: View {
    @Environment(\.dismissImmersiveSpace)
    private var dismissImmersiveSpace

    var body: some View {
        Button("Close Solar System") {
            Task {
                await dismissImmersiveSpace()
            }
        }
    }
}
```

The dismiss action runs asynchronously, like the open action. You don’t need to specify an identifier when dismissing an immersive space because there can only be one immersive space open at a time.

### Present an immersive space at launch

When an app launches, it opens an instance of the first scene that’s listed in the app’s body. When opening an immersive space at launch, the system may still ask the user for a preferred device with which to display the content.

## Initializers

- **init(content:)**: Creates a remote immersive space.
- **init(for:content:)**: Creates the remote immersive space for a specified type of presented data.
- **init(for:content:defaultValue:)**: Creates the remote immersive space for a specified type of presented data, and a default value, if the data is not set.
- **init(id:content:)**: Creates the remote immersive space associated with the specified identifier.
- **init(id:for:content:)**: Creates the remote immersive space associated with an identifier for a specified type of presented data.
- **init(id:for:content:defaultValue:)**: Creates the remote immersive space associated with an identifier for a specified type of presented data, and a default value, if the data is not set.

## Handling remote immersive spaces

- **RemoteDeviceIdentifier**: An opaque type that identifies a remote device displaying scene content in a [RemoteImmersiveSpace](RemoteImmersiveSpace.zh-Hans.md).

## Conforms To

- Scene

