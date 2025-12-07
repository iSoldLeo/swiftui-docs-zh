--- 来源：https://developer.apple.com/documentation/SwiftUI/RemoteDeviceIdentifier
抓取时间：2025-12-02T17:22:02Z

---

# RemoteDeviceIdentifier

**Structure**

一个不透明类型，用于标识在 [RemoteImmersiveSpace](RemoteImmersiveSpace.zh-Hans.md) 中显示场景内容的远程设备。

## 声明

```swift
struct RemoteDeviceIdentifier
```

## 概述

在远程场景中，可通过 [remoteDeviceIdentifier](EnvironmentValues/remoteDeviceIdentifier.zh-Hans.md) 环境属性访问此标识符，以获取该场景设备的标识符。

当在本地设备上呈现的上下文中访问此标识符时，其值为 `nil`。

此标识符也可用于初始化与远程设备关联的 `ARKitSession`。

```swift
struct SolarSystem: CompositorContent {
    @Environment(\.remoteDeviceIdentifier) private var deviceID

    var body: some CompositorContent {
        RemoteImmersiveSpace {
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
}
```

## 实例属性

- **cDevice**：返回与此设备关联的 `ar_device`。

## 处理远程沉浸式空间

- **RemoteImmersiveSpace**：在远程设备的无限空间中呈现内容的场景。

## 符合以下标准

- Equatable

- Hashable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/RemoteDeviceIdentifier
crawled: 2025-12-02T17:22:02Z
---

# RemoteDeviceIdentifier

**Structure**

An opaque type that identifies a remote device displaying scene content in a [RemoteImmersiveSpace](RemoteImmersiveSpace.zh-Hans.md).

## Declaration

```swift
struct RemoteDeviceIdentifier
```

## Overview

Access this from the [remoteDeviceIdentifier](EnvironmentValues/remoteDeviceIdentifier.zh-Hans.md) environment property in a remote scene to get the identifier for that scene’s device.

When accessed in a context that is being presented on the local device, this value will be `nil`.

This identifier can also be used to initialize an `ARKitSession` associated with the remote device.

```swift
struct SolarSystem: CompositorContent {
    @Environment(\.remoteDeviceIdentifier) private var deviceID

    var body: some CompositorContent {
        RemoteImmersiveSpace {
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
}
```



## Instance Properties

- **cDevice**: Returns the `ar_device` associated with this device.

## Handling remote immersive spaces

- **RemoteImmersiveSpace**: A scene that presents its content in an unbounded space on a remote device.

## Conforms To

- Equatable
- Hashable
- Sendable
- SendableMetatype

