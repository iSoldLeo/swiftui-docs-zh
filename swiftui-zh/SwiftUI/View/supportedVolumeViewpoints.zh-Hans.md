--- 来源：https://developer.apple.com/documentation/SwiftUI/View/supportedVolumeViewpoints(_:)

抓取时间：2025-12-02T17:21:38Z

---

# supportedVolumeViewpoints(_:)

**实例方法**

指定卷中窗口栏和装饰器支持的视点。

## 声明

```swift
nonisolated func supportedVolumeViewpoints(_ viewpoints: SquareAzimuth.Set) -> some View

```

## 说明

此方法默认支持所有视点，并决定窗口栏和装饰器在用户于卷中移动时会“跟随”到哪些视点。

## 与卷交互

- **onVolumeViewpointChange(updateStrategy:initial:_:)**：添加卷视点改变时要执行的操作。

- **VolumeViewpointUpdateStrategy**：描述何时调用提供给 [onVolumeViewpointChange(updateStrategy:initial:_:)](onVolumeViewpointChange_updateStrategy_initial.zh-Hans.md) 的动作的类型。

- **Viewpoint3D**：描述观察方向的类型。

- **SquareAzimuth**：描述沿水平面观察方向的类型，并捕捉到四个方向。

- **WorldAlignmentBehavior**：表示场景的世界对齐行为的类型。

- **volumeWorldAlignment(_:)**：指定体积在世界中移动时的对齐方式。

- **WorldScalingBehavior**：指定窗口在世界中的缩放行为。

- **defaultWorldScaling(_:)**：指定窗口的世界缩放行为。

- **WorldScalingCompensation**：指示返回的指标是否会考虑动态缩放。

- **worldTrackingLimitations**：设备当前跟踪用户周围环境的限制。

- **WorldTrackingLimitation**：用于表示跟踪用户周围环境限制的结构体。

- **SurfaceSnappingInfo**：表示窗口场景捕捉状态信息的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/View/supportedVolumeViewpoints(_:)
crawled: 2025-12-02T17:21:38Z
---

# supportedVolumeViewpoints(_:)

**Instance Method**

Specifies which viewpoints are supported for the window bar and ornaments in a volume.

## Declaration

```swift
nonisolated func supportedVolumeViewpoints(_ viewpoints: SquareAzimuth.Set) -> some View

```

## Discussion

This defaults to all viewpoints and determines which viewpoints the window bar and ornaments will ‘follow’ the user to as they move around the volume.

## Interacting with volumes

- **onVolumeViewpointChange(updateStrategy:initial:_:)**: Adds an action to perform when the viewpoint of the volume changes.
- **VolumeViewpointUpdateStrategy**: A type describing when the action provided to [onVolumeViewpointChange(updateStrategy:initial:_:)](onVolumeViewpointChange_updateStrategy_initial.zh-Hans.md) should be called.
- **Viewpoint3D**: A type describing what direction something is being viewed from.
- **SquareAzimuth**: A type describing what direction something is being viewed from along the horizontal plane and snapped to 4 directions.
- **WorldAlignmentBehavior**: A type representing the world alignment behavior for a scene.
- **volumeWorldAlignment(_:)**: Specifies how a volume should be aligned when moved in the world.
- **WorldScalingBehavior**: Specifies the scaling behavior a window should have within the world.
- **defaultWorldScaling(_:)**: Specify the world scaling behavior for the window.
- **WorldScalingCompensation**: Indicates whether returned metrics will take dynamic scaling into account.
- **worldTrackingLimitations**: The current limitations of the device tracking the user’s surroundings.
- **WorldTrackingLimitation**: A structure to represent limitations of tracking the user’s surroundings.
- **SurfaceSnappingInfo**: A type representing information about the window scenes snap state.

