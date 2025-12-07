--- 来源：https://developer.apple.com/documentation/swiftui/squareazimuth

抓取时间：2025-12-04T11:27:57Z

---

# SquareAzimuth

**Enumeration**

一种描述物体在水平面上的观察方向的类型，并可捕捉到四个方向。

## 声明

```swift
@frozen enum SquareAzimuth
```

## 结构体

- **SquareAzimuth.Set**

## 枚举类型

- **SquareAzimuth.back**：具有水平角度等于 `180°` 的方向

- **SquareAzimuth.front**：具有水平角度等于 `0°` 的方向。

- **SquareAzimuth.left**：具有与 `270°` 相等的水平角度的方向。

- **SquareAzimuth.right**：具有与 `90°` 相等的水平角度的方向。

## 初始化器

- **init(closestToAzimuth:)**：创建一个 [SquareAzimuth](SquareAzimuth.zh-Hans.md) 实例，其方向的水平角度最接近提供的方位角。

## 实例属性

- **orientation**：一个 3D 旋转，该旋转会捕捉到四个边之一的中心。

## 与体交互

- **onVolumeViewpointChange(updateStrategy:initial:_:)**：添加一个在体视点改变时要执行的操作。

- **supportedVolumeViewpoints(_:)**：指定体中窗口栏和装饰物支持的视角。

- **VolumeViewpointUpdateStrategy**：描述何时调用提供给 [onVolumeViewpointChange(updateStrategy:initial:_:)](View/onVolumeViewpointChange_updateStrategy_initial.zh-Hans.md) 的操作的类型。

- **Viewpoint3D**：描述观察方向的类型。

- **WorldAlignmentBehavior**：表示场景的世界对齐行为的类型。

- **volumeWorldAlignment(_:)**：指定体在世界中移动时应如何对齐。

- **WorldScalingBehavior**：指定窗口在世界中的缩放行为。

- **defaultWorldScaling(_:)**：指定窗口的世界缩放行为。

- **WorldScalingCompensation**：指示返回的度量是否会考虑动态缩放。

- **worldTrackingLimitations**：设备当前跟踪用户周围环境的限制。

- **WorldTrackingLimitation**：用于表示跟踪用户周围环境限制的结构体。

- **SurfaceSnappingInfo**：表示窗口场景捕捉状态信息的类型。

## 符合以下规范

- BitwiseCopyable

- CaseIterable

- Copyable

- Equatable

- Hashable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/swiftui/squareazimuth
crawled: 2025-12-04T11:27:57Z
---

# SquareAzimuth

**Enumeration**

A type describing what direction something is being viewed from along the horizontal plane and snapped to 4 directions.

## Declaration

```swift
@frozen enum SquareAzimuth
```

## Structures

- **SquareAzimuth.Set**

## Enumeration Cases

- **SquareAzimuth.back**: Has an orientation with an horizontal angle equal to `180°`
- **SquareAzimuth.front**: Has an orientation with an horizontal angle equal to `0°`.
- **SquareAzimuth.left**: Has an orientation with an horizontal angle equal to `270°`.
- **SquareAzimuth.right**: Has an orientation with an horizontal angle equal to `90°`.

## Initializers

- **init(closestToAzimuth:)**: Creates a [SquareAzimuth](SquareAzimuth.zh-Hans.md) case with an orientation that has a horizontal angle closest to the provided azimuth.

## Instance Properties

- **orientation**: A 3D rotation that is snapped to the center of one of the four sides.

## Interacting with volumes

- **onVolumeViewpointChange(updateStrategy:initial:_:)**: Adds an action to perform when the viewpoint of the volume changes.
- **supportedVolumeViewpoints(_:)**: Specifies which viewpoints are supported for the window bar and ornaments in a volume.
- **VolumeViewpointUpdateStrategy**: A type describing when the action provided to [onVolumeViewpointChange(updateStrategy:initial:_:)](View/onVolumeViewpointChange_updateStrategy_initial.zh-Hans.md) should be called.
- **Viewpoint3D**: A type describing what direction something is being viewed from.
- **WorldAlignmentBehavior**: A type representing the world alignment behavior for a scene.
- **volumeWorldAlignment(_:)**: Specifies how a volume should be aligned when moved in the world.
- **WorldScalingBehavior**: Specifies the scaling behavior a window should have within the world.
- **defaultWorldScaling(_:)**: Specify the world scaling behavior for the window.
- **WorldScalingCompensation**: Indicates whether returned metrics will take dynamic scaling into account.
- **worldTrackingLimitations**: The current limitations of the device tracking the user’s surroundings.
- **WorldTrackingLimitation**: A structure to represent limitations of tracking the user’s surroundings.
- **SurfaceSnappingInfo**: A type representing information about the window scenes snap state.

## Conforms To

- BitwiseCopyable
- CaseIterable
- Copyable
- Equatable
- Hashable
- Sendable
- SendableMetatype

