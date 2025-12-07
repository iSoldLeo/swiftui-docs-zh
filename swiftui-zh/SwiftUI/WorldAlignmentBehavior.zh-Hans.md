--- 来源：https://developer.apple.com/documentation/SwiftUI/WorldAlignmentBehavior
抓取时间：2025-12-02T17:21:40Z

---

# WorldAlignmentBehavior

**Structure**

表示场景世界对齐行为的类型。

## 声明

```swift
struct WorldAlignmentBehavior
```

## 概述

可以将此类型的值提供给 [volumeWorldAlignment(_:)](scene/volumeWorldAlignment.zh-Hans.md) 场景修改器，以控制体积在重新定位时应保持的世界对齐。默认值为 [automatic](WorldAlignmentBehavior/automatic.zh-Hans.md)。

## 类型属性

- **adaptive**：当体积被抬升到高于视线水平时，体积会倾斜，使正面始终完全可见。

- **automatic**：系统默认的世界对齐行为。

- **gravityAligned**：为了保持与重力对齐，体积不会倾斜。

## 与体积交互

- **onVolumeViewpointChange(updateStrategy:initial:_:)**：添加一个在体积视角改变时执行的操作。

- **supportedVolumeViewpoints(_:)**：指定体积中的窗口栏和装饰物支持的视角。

- **VolumeViewpointUpdateStrategy**：描述何时调用提供给 [onVolumeViewpointChange(updateStrategy:initial:_:)](View/onVolumeViewpointChange_updateStrategy_initial.zh-Hans.md) 的操作的类型。

- **Viewpoint3D**：描述当前观察方向的类型。

- **SquareAzimuth**：描述当前观察方向的类型（沿水平面并捕捉到四个方向）。

- **volumeWorldAlignment(_:)**：指定体积在世界空间中移动时的对齐方式。

- **WorldScalingBehavior**：指定窗口在世界空间中的缩放行为。

- **defaultWorldScaling(_:)**：指定窗口的世界缩放行为。

- **WorldScalingCompensation**：指示返回的指标是否会考虑动态缩放。

- **worldTrackingLimitations**：设备当前跟踪用户周围环境的限制。

- **WorldTrackingLimitation**：用于表示跟踪用户周围环境限制的结构。

- **SurfaceSnappingInfo**：表示窗口场景捕捉状态信息的类型。

## 符合以下标准

- Equatable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/WorldAlignmentBehavior
crawled: 2025-12-02T17:21:40Z
---

# WorldAlignmentBehavior

**Structure**

A type representing the world alignment behavior for a scene.

## Declaration

```swift
struct WorldAlignmentBehavior
```

## Overview

A value of this type can be provided to the [volumeWorldAlignment(_:)](scene/volumeWorldAlignment.zh-Hans.md) scene modifier to control the world alignment volumes should maintain as they are repositioned. The default value is [automatic](WorldAlignmentBehavior/automatic.zh-Hans.md).

## Type Properties

- **adaptive**: When lifted above eye level, the volume will tilt so the front remains fully visible.
- **automatic**: The world alignment behavior that is standard for the system.
- **gravityAligned**: The volume will not tilt so as to remain aligned with gravity.

## Interacting with volumes

- **onVolumeViewpointChange(updateStrategy:initial:_:)**: Adds an action to perform when the viewpoint of the volume changes.
- **supportedVolumeViewpoints(_:)**: Specifies which viewpoints are supported for the window bar and ornaments in a volume.
- **VolumeViewpointUpdateStrategy**: A type describing when the action provided to [onVolumeViewpointChange(updateStrategy:initial:_:)](View/onVolumeViewpointChange_updateStrategy_initial.zh-Hans.md) should be called.
- **Viewpoint3D**: A type describing what direction something is being viewed from.
- **SquareAzimuth**: A type describing what direction something is being viewed from along the horizontal plane and snapped to 4 directions.
- **volumeWorldAlignment(_:)**: Specifies how a volume should be aligned when moved in the world.
- **WorldScalingBehavior**: Specifies the scaling behavior a window should have within the world.
- **defaultWorldScaling(_:)**: Specify the world scaling behavior for the window.
- **WorldScalingCompensation**: Indicates whether returned metrics will take dynamic scaling into account.
- **worldTrackingLimitations**: The current limitations of the device tracking the user’s surroundings.
- **WorldTrackingLimitation**: A structure to represent limitations of tracking the user’s surroundings.
- **SurfaceSnappingInfo**: A type representing information about the window scenes snap state.

## Conforms To

- Equatable
- Sendable
- SendableMetatype

