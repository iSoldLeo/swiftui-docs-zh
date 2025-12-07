---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/supportsRemoteScenes
抓取时间： 2025-12-03T06:08:17Z
---

# 支持远程场景

**实例属性**

表示当前设备是否支持在远程设备上显示[RemoteImmersiveSpace](../RemoteImmersiveSpace.zh-Hans.md)。

## 声明

```swift
var supportsRemoteScenes: Bool { get }
```

## 讨论

使用此功能可在远程设备上显示应用程序的内容。

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


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/supportsRemoteScenes
crawled: 2025-12-03T06:08:17Z
---

# supportsRemoteScenes

**Instance Property**

Indicates if the current device supports presenting a [RemoteImmersiveSpace](../RemoteImmersiveSpace.zh-Hans.md) on a remote device.

## Declaration

```swift
var supportsRemoteScenes: Bool { get }
```

## Discussion

Use this to provide affordances for displaying your app’s content on a remote device.

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

