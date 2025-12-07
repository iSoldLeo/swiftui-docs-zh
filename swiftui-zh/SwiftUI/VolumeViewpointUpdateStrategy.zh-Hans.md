---
来源： https://developer.apple.com/documentation/SwiftUI/VolumeViewpointUpdateStrategy
抓取时间： 2025-12-02T17:21:39Z
---

# VolumeViewpointUpdateStrategy

**Structure**

描述[onVolumeViewpointChange(updateStrategy:initial:_:)](View/onVolumeViewpointChange_updateStrategy_initial.zh-Hans.md) 提供的操作何时应被调用的类型。

### 声明

```swift
struct VolumeViewpointUpdateStrategy
```

## 类型属性

- **all**：所有视图更改都应运行该操作。
- **supported**：只有当新视点等同于通过 [supportedVolumeViewpoints(_:)](View/supportedVolumeViewpoints.zh-Hans.md) 提供的值之一时，才应运行该操作。

## 与体积交互

- **onVolumeViewpointChange(updateStrategy:initial:_:)**：添加音量视角发生变化时要执行的操作。
- **supportedVolumeViewpoints(_:)**：指定卷中的窗口栏和装饰物支持哪些视点。
- **Viewpoint3D**：描述从哪个方向查看某物的类型。
- **SquareAzimuth**：描述沿水平面从哪个方向观看某物的类型，并向 4 个方向折叠。
- **WorldAlignmentBehavior**：表示场景的世界对齐行为的类型。
- **volumeWorldAlignment(_:)**：指定体积在世界中移动时的对齐方式。
- **WorldScalingBehavior**：指定窗口在世界中的缩放行为。
- **defaultWorldScaling(_:)**：为窗口指定世界缩放行为。
- **WorldScalingCompensation**：表示返回的度量是否将动态缩放考虑在内。
- **worldTrackingLimitations**：设备跟踪用户周围环境的当前限制。
- **WorldTrackingLimitation**：表示跟踪用户周围环境限制的结构。
- **SurfaceSnappingInfo**：表示窗口场景捕捉状态信息的类型。

## 符合

- 等价
- 可发送
- 可发送元数据类型


---
source: https://developer.apple.com/documentation/SwiftUI/VolumeViewpointUpdateStrategy
crawled: 2025-12-02T17:21:39Z
---

# VolumeViewpointUpdateStrategy

**Structure**

A type describing when the action provided to [onVolumeViewpointChange(updateStrategy:initial:_:)](View/onVolumeViewpointChange_updateStrategy_initial.zh-Hans.md) should be called.

## Declaration

```swift
struct VolumeViewpointUpdateStrategy
```

## Type Properties

- **all**: The action should be run for all viewpoint changes.
- **supported**: The action should only be run when the new viewpoint is equivalent to one of the values provided through [supportedVolumeViewpoints(_:)](View/supportedVolumeViewpoints.zh-Hans.md).

## Interacting with volumes

- **onVolumeViewpointChange(updateStrategy:initial:_:)**: Adds an action to perform when the viewpoint of the volume changes.
- **supportedVolumeViewpoints(_:)**: Specifies which viewpoints are supported for the window bar and ornaments in a volume.
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

## Conforms To

- Equatable
- Sendable
- SendableMetatype

