--- 来源：https://developer.apple.com/documentation/SwiftUI/Viewpoint3D
抓取时间：2025-12-02T16:21:27Z

---

# Viewpoint3D

**Structure**

描述视角方向的类型。

## 声明

```swift
struct Viewpoint3D
```

## 实例属性

- **squareAzimuth**：描述视角方向（水平方向）的值。

## 类型属性

- **standard**：表示视角方向（正前方）。

## 与体积交互

- **onVolumeViewpointChange(updateStrategy:initial:_:)**：添加在体积视角改变时执行的操作。

- **supportedVolumeViewpoints(_:)**：指定体中窗口栏和装饰物支持的视点。

- **VolumeViewpointUpdateStrategy**：描述何时调用提供给 [onVolumeViewpointChange(updateStrategy:initial:_:)](View/onVolumeViewpointChange_updateStrategy_initial.zh-Hans.md) 的操作的类型。

- **SquareAzimuth**：描述沿水平面观察物体的方向，并捕捉到四个方向的类型。

- **WorldAlignmentBehavior**：表示场景的世界对齐行为的类型。

- **volumeWorldAlignment(_:)**：指定体在世界中移动时应如何对齐。

- **WorldScalingBehavior**：指定窗口在世界中的缩放行为。

- **defaultWorldScaling(_:)**：指定窗口的世界缩放行为。

- **WorldScalingCompensation**：指示返回的指标是否会考虑动态缩放。

- **worldTrackingLimitations**：设备当前跟踪用户周围环境的限制。

- **WorldTrackingLimitation**：用于表示跟踪用户周围环境限制的结构体。

- **SurfaceSnappingInfo**：表示窗口场景捕捉状态信息的类型。

## 符合以下协议：

- CustomDebugStringConvertible

- Equatable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/Viewpoint3D
crawled: 2025-12-02T16:21:27Z
---

# Viewpoint3D

**Structure**

A type describing what direction something is being viewed from.

## Declaration

```swift
struct Viewpoint3D
```

## Instance Properties

- **squareAzimuth**: A value describing what direction something is being viewed from along the horizontal plane.

## Type Properties

- **standard**: A value that represents being viewed from the front middle.

## Interacting with volumes

- **onVolumeViewpointChange(updateStrategy:initial:_:)**: Adds an action to perform when the viewpoint of the volume changes.
- **supportedVolumeViewpoints(_:)**: Specifies which viewpoints are supported for the window bar and ornaments in a volume.
- **VolumeViewpointUpdateStrategy**: A type describing when the action provided to [onVolumeViewpointChange(updateStrategy:initial:_:)](View/onVolumeViewpointChange_updateStrategy_initial.zh-Hans.md) should be called.
- **SquareAzimuth**: A type describing what direction something is being viewed from along the horizontal plane and snapped to 4 directions.
- **WorldAlignmentBehavior**: A type representing the world alignment behavior for a scene.
- **volumeWorldAlignment(_:)**: Specifies how a volume should be aligned when moved in the world.
- **WorldScalingBehavior**: Specifies the scaling behavior a window should have within the world.
- **defaultWorldScaling(_:)**: Specify the world scaling behavior for the window.
- **WorldScalingCompensation**: Indicates whether returned metrics will take dynamic scaling into account.
- **worldTrackingLimitations**: The current limitations of the device tracking the user’s surroundings.
- **WorldTrackingLimitation**: A structure to represent limitations of tracking the user’s surroundings.
- **SurfaceSnappingInfo**: A type representing information about the window scenes snap state.

## Conforms To

- CustomDebugStringConvertible
- Equatable
- Sendable
- SendableMetatype

