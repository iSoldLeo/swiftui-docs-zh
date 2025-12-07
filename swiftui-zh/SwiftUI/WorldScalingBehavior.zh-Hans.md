---
来源： https://developer.apple.com/documentation/SwiftUI/WorldScalingBehavior
抓取时间： 2025-12-02T17:21:41Z
---

# 世界缩放行为

**Structure**

指定窗口在世界中的缩放行为。

## 声明

```swift
struct WorldScalingBehavior
```

## 概览

默认情况下，常规[WindowGroup](WindowGroup.zh-Hans.md) 使用[dynamic](WorldScalingBehavior/dynamic.zh-Hans.md) 的缩放行为，而使用[volumetric](WindowStyle/volumetric.zh-Hans.md) 的窗口具有固定缩放比例。

动态缩放是指窗口在保持角度大小不变的情况下，随着移动距离的增加而放大。固定比例是指窗口将保持其在世界上的物理尺寸。

有关详细信息，请参阅《人机界面指南》中的[doc://com.apple.documentation/design/Human-Interface-Guidelines/spatial-layout#Scale]。

## 类型属性

- **automatic**：窗口样式的标准缩放行为。
- **dynamic**：窗口会随着移动距离的增加而缩放，但角度大小保持不变。

## 与体积交互

- **onVolumeViewpointChange(updateStrategy:initial:_:)**：添加一个当体的视角发生变化时要执行的操作。
- **supportedVolumeViewpoints(_:)**：指定卷中的窗口栏和装饰物支持哪些视点。
- **VolumeViewpointUpdateStrategy**：描述何时应调用提供给 [onVolumeViewpointChange(updateStrategy:initial:_:)](View/onVolumeViewpointChange_updateStrategy_initial.zh-Hans.md) 的操作的类型。
- **Viewpoint3D**：描述从哪个方向观看某物的类型。
- **SquareAzimuth**：描述沿水平面从哪个方向观看某物的类型，并向 4 个方向折叠。
- **WorldAlignmentBehavior**：表示场景的世界对齐行为的类型。
- **volumeWorldAlignment(_:)**：指定体积在世界中移动时的对齐方式。
- **defaultWorldScaling(_:)**：指定窗口的世界缩放行为。
- **WorldScalingCompensation**：表示返回的度量是否将动态缩放考虑在内。
- **worldTrackingLimitations**：设备跟踪用户周围环境的当前限制。
- **WorldTrackingLimitation**：表示跟踪用户周围环境限制的结构。
- **SurfaceSnappingInfo**：表示窗口场景捕捉状态信息的类型。

## 符合

- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/WorldScalingBehavior
crawled: 2025-12-02T17:21:41Z
---

# WorldScalingBehavior

**Structure**

Specifies the scaling behavior a window should have within the world.

## Declaration

```swift
struct WorldScalingBehavior
```

## Overview

By default, a regular [WindowGroup](WindowGroup.zh-Hans.md) uses a scaling behavior of [dynamic](WorldScalingBehavior/dynamic.zh-Hans.md), and a window with [volumetric](WindowStyle/volumetric.zh-Hans.md) has a fixed scale.

Dynamic scale means the window will scale larger as it moves further away, maintaining the same angular size. Fixed scale means the window will keep its physical size in the world.

For further information, see [doc://com.apple.documentation/design/Human-Interface-Guidelines/spatial-layout#Scale] in the Human Interface Guidelines.

## Type Properties

- **automatic**: The scaling behavior that is standard for the window’s style.
- **dynamic**: The window will scale up as it moves further away, maintaining the same angular size.

## Interacting with volumes

- **onVolumeViewpointChange(updateStrategy:initial:_:)**: Adds an action to perform when the viewpoint of the volume changes.
- **supportedVolumeViewpoints(_:)**: Specifies which viewpoints are supported for the window bar and ornaments in a volume.
- **VolumeViewpointUpdateStrategy**: A type describing when the action provided to [onVolumeViewpointChange(updateStrategy:initial:_:)](View/onVolumeViewpointChange_updateStrategy_initial.zh-Hans.md) should be called.
- **Viewpoint3D**: A type describing what direction something is being viewed from.
- **SquareAzimuth**: A type describing what direction something is being viewed from along the horizontal plane and snapped to 4 directions.
- **WorldAlignmentBehavior**: A type representing the world alignment behavior for a scene.
- **volumeWorldAlignment(_:)**: Specifies how a volume should be aligned when moved in the world.
- **defaultWorldScaling(_:)**: Specify the world scaling behavior for the window.
- **WorldScalingCompensation**: Indicates whether returned metrics will take dynamic scaling into account.
- **worldTrackingLimitations**: The current limitations of the device tracking the user’s surroundings.
- **WorldTrackingLimitation**: A structure to represent limitations of tracking the user’s surroundings.
- **SurfaceSnappingInfo**: A type representing information about the window scenes snap state.

## Conforms To

- Equatable
- Hashable
- Sendable
- SendableMetatype

