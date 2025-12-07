---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/remoteDeviceIdentifier
抓取时间： 2025-12-03T06:08:13Z
---

# remoteDeviceIdentifier

**实例属性**

一个不透明对象，用于标识显示场景（从该对象访问此值）的设备。

### 声明

```swift
var remoteDeviceIdentifier: RemoteDeviceIdentifier? { get }
```

## 讨论

在本地设备上显示的上下文中访问时，该值将为`nil`。

该标识符也可用于初始化与远程设备相关联的`ARKitSession`。

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




---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/remoteDeviceIdentifier
crawled: 2025-12-03T06:08:13Z
---

# remoteDeviceIdentifier

**Instance Property**

An opaque object that identifies the device on which the scene (from which this value is accessed from) is being presented on.

## Declaration

```swift
var remoteDeviceIdentifier: RemoteDeviceIdentifier? { get }
```

## Discussion

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



