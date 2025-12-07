--- 来源：https://developer.apple.com/documentation/SwiftUI/SurfaceSnappingInfo
抓取时间：2025-12-02T17:21:45Z

---

# SurfaceSnappingInfo

**Structure**

一种表示窗口场景吸附状态信息的类型。

## 声明

```swift
struct SurfaceSnappingInfo
```

## 概述

使用提供的 [SurfaceSnappingInfo](SurfaceSnappingInfo.zh-Hans.md) 来修改视图的内容。

```swift
struct LightFixtureView: View {
    @Environment(\.surfaceSnappingInfo)
    var snappingInfo: SurfaceSnappingInfo

    var body: some View {
        if snappingInfo.isSnapped {
            switch SurfaceSnappingInfo.authorizationStatus {
                case .authorized:
                    switch snappingInfo.classification {
                        case .table:
                            LampView()
                        case .floor:
                            FloorLampView()
                        default:
                            DefaultLampView()
                    }
                default:
                    DefaultLampView()
            }
        } else {
            FloatingOrbLampView()
        }
    }
}
```

体积的底部可以吸附到水平表面，窗口的背面可以吸附到垂直表面。

## 实例属性

- **classification**：一种提供场景吸附到的表面分类信息的类型。仅当场景已吸附到物理表面且 `authorizationStatus` 为 `.authorized` 时，此属性才有值。

- **isSnapped**：表示场景当前是否吸附到物理表面的值。

## 类型属性

- **authorizationStatus**：表示用户是否已授权提供有关场景吸附到的表面的更详细信息的值。要请求此详细的表面信息，请在 `Info.plist` 文件中，将 `UIWantsDetailedSurfaceInfo` 设置为 `YES`，并将 `NSWorldSensingUsageDescription` 设置为描述您的应用请求此信息的原因。

## 枚举

- **SurfaceSnappingInfo.AuthorizationStatus**：表示用户是否已授予权限，以提供有关场景所吸附表面的更详细信息。

## 与体交互

- **onVolumeViewpointChange(updateStrategy:initial:_:)**：添加在体视点改变时要执行的操作。

- **supportedVolumeViewpoints(_:)**：指定体中窗口栏和装饰物支持的视点。

- **VolumeViewpointUpdateStrategy**：描述何时应调用提供给 [onVolumeViewpointChange(updateStrategy:initial:_:)](View/onVolumeViewpointChange_updateStrategy_initial.zh-Hans.md) 的操作的类型。

- **Viewpoint3D**：描述当前观察方向的类型。

- **SquareAzimuth**：描述当前沿水平面观察并吸附到四个方向的类型。

- **WorldAlignmentBehavior**：表示场景的世界对齐行为的类型。

- **volumeWorldAlignment(_:)**：指定体积在世界空间中移动时的对齐方式。

- **WorldScalingBehavior**：指定窗口在世界中的缩放行为。

- **defaultWorldScaling(_:)**：指定窗口的世界缩放行为。

- **WorldScalingCompensation**：指示返回的指标是否会考虑动态缩放。

- **worldTrackingLimitations**：设备跟踪用户周围环境的当前限制。

- **WorldTrackingLimitation**：表示跟踪用户周围环境限制的结构。

## 符合以下协议：

- CustomDebugStringConvertible

- Equatable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/SurfaceSnappingInfo
crawled: 2025-12-02T17:21:45Z
---

# SurfaceSnappingInfo

**Structure**

A type representing information about the window scenes snap state.

## Declaration

```swift
struct SurfaceSnappingInfo
```

## Overview

Use the provided [SurfaceSnappingInfo](SurfaceSnappingInfo.zh-Hans.md) to modify the contents of your view.

```swift
struct LightFixtureView: View {
    @Environment(\.surfaceSnappingInfo)
    var snappingInfo: SurfaceSnappingInfo

    var body: some View {
        if snappingInfo.isSnapped {
            switch SurfaceSnappingInfo.authorizationStatus {
                case .authorized:
                    switch snappingInfo.classification {
                        case .table:
                            LampView()
                        case .floor:
                            FloorLampView()
                        default:
                            DefaultLampView()
                    }
                default:
                    DefaultLampView()
            }
        } else {
            FloatingOrbLampView()
        }
    }
}
```

The bottom of volumes may snap to horizontal surfaces and the back of windows may snap to vertical surfaces.

## Instance Properties

- **classification**: A type that provides information about the surface classification the scene is snapped to. This property only has a value if the scene is snapped and `authorizationStatus` is `.authorized`.
- **isSnapped**: A value that represents whether the scene is currently snapped to a physical surface or not.

## Type Properties

- **authorizationStatus**: A value that represents whether the user has authorized providing more detailed information about the surface scenes are snapped to. To request this detailed surface information, in your `Info.plist` file, set `UIWantsDetailedSurfaceInfo` to `YES` and set `NSWorldSensingUsageDescription` to provide a description of why your app is requesting this information.

## Enumerations

- **SurfaceSnappingInfo.AuthorizationStatus**: A type representing whether the user has granted permissions to provide more detailed information about the surface a scene is snapped to.

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

## Conforms To

- CustomDebugStringConvertible
- Equatable
- Sendable
- SendableMetatype

