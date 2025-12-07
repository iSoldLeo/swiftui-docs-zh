---
来源： https://developer.apple.com/documentation/SwiftUI/WorldScalingCompensation
抓取时间： 2025-12-02T17:21:43Z
---

# 世界缩放补偿

**Structure**

表示返回的度量值是否考虑了动态缩放。

## 声明

```swift
struct WorldScalingCompensation
```

## 概览

在 visionOS 上，使用[defaultWorldScaling(_:)](scene/defaultWorldScaling.zh-Hans.md)修饰符的窗口场景或体积场景在用户重新定位时可能会动态缩放。在这种情况下，[PhysicalMetric](PhysicalMetric.zh-Hans.md) 或 [PhysicalMetricsConverter](PhysicalMetricsConverter.zh-Hans.md) 值返回的度量值可能与`RealityView` 的单位一致，也可能不一致。

世界比例补偿允许您指定是否考虑这种比例。如果数值为 [unscaled](WorldScalingCompensation/unscaled.zh-Hans.md)，则它们将与用户周围环境的物理指标相对应，与动态比例无关。如果[scaled](WorldScalingCompensation/scaled.zh-Hans.md)，它们将根据场景进行适当缩放，这意味着它们将与该场景中`RealityView`的默认坐标系相匹配。

### 类型属性

- **scaled**：返回经过适当缩放以匹配其场景坐标系的度量值，包括任何世界缩放行为。
- **unscaled**：返回与用户周围环境比例相匹配的度量值，与场景的世界缩放行为无关。

## 与体积互动

- **onVolumeViewpointChange(updateStrategy:initial:_:)**：添加一个在体的视角发生变化时执行的动作。
- **supportedVolumeViewpoints(_:)**：指定卷中的窗口栏和装饰物支持哪些视点。
- **VolumeViewpointUpdateStrategy**：描述何时应调用提供给 [onVolumeViewpointChange(updateStrategy:initial:_:)](View/onVolumeViewpointChange_updateStrategy_initial.zh-Hans.md) 的操作的类型。
- **Viewpoint3D**：描述从哪个方向观看某物的类型。
- **SquareAzimuth**：描述沿水平面从哪个方向观看某物的类型，并向 4 个方向折叠。
- **WorldAlignmentBehavior**：表示场景的世界对齐行为的类型。
- **volumeWorldAlignment(_:)**：指定体积在世界中移动时的对齐方式。
- **WorldScalingBehavior**：指定窗口在世界中的缩放行为。
- **defaultWorldScaling(_:)**：为窗口指定世界缩放行为。
- **worldTrackingLimitations**：设备跟踪用户周围环境的当前限制。
- **WorldTrackingLimitation**：表示跟踪用户周围环境限制的结构。
- **SurfaceSnappingInfo**：表示窗口场景捕捉状态信息的类型。

## 符合

- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/WorldScalingCompensation
crawled: 2025-12-02T17:21:43Z
---

# WorldScalingCompensation

**Structure**

Indicates whether returned metrics will take dynamic scaling into account.

## Declaration

```swift
struct WorldScalingCompensation
```

## Overview

On visionOS, a window scene or a volume scene with the [defaultWorldScaling(_:)](scene/defaultWorldScaling.zh-Hans.md) modifier may scale dynamically when the user repositions it. In those cases, the metrics returned by a [PhysicalMetric](PhysicalMetric.zh-Hans.md) or [PhysicalMetricsConverter](PhysicalMetricsConverter.zh-Hans.md) value may or may not correspond to the units of a `RealityView`.

World scale compensation lets you specify if this scaling is taken into account. If the values are [unscaled](WorldScalingCompensation/unscaled.zh-Hans.md), they will correspond to the physical metrics of the user’s surroundings, regardless of dynamic scale. If [scaled](WorldScalingCompensation/scaled.zh-Hans.md), they will be scaled appropriately for the scene, which means they will match the default coordinate system of a `RealityView` in that scene.

## Type Properties

- **scaled**: Returns metrics that are scaled appropriately to match the coordinate system of their scene, including any world scaling behavior.
- **unscaled**: Returns metrics that match the scale of the user’s surroundings, regardless of the world scaling behavior of their scene.

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
- **worldTrackingLimitations**: The current limitations of the device tracking the user’s surroundings.
- **WorldTrackingLimitation**: A structure to represent limitations of tracking the user’s surroundings.
- **SurfaceSnappingInfo**: A type representing information about the window scenes snap state.

## Conforms To

- Equatable
- Hashable
- Sendable
- SendableMetatype

