---
来源： https://developer.apple.com/documentation/SwiftUI/WorldTrackingLimitation
抓取时间： 2025-12-02T17:21:44Z
---

# 世界追踪限制

**Structure**

表示追踪用户周围环境限制的结构。

## 声明

```swift
struct WorldTrackingLimitation
```

## 概览

读取 [worldTrackingLimitations](EnvironmentValues/worldTrackingLimitations.zh-Hans.md) 环境值时，您会收到一组世界跟踪限制。该值会告诉您设备当前面临的限制。如果由于环境（如照明）的变化而出现任何限制，则会相应地更新设置。例如，当世界跟踪限制发生变化时，下面的[Text](Text.zh-Hans.md) 视图会自动更新：

```swift
@Environment(\.worldTrackingLimitations)
private var worldTrackingLimitations

var body: some View {
    Text("Can track translation?" + worldTrackingLimitations
        .contains(.translation) ? "No" : "Yes")
}
```

## 类型属性

- **orientation**：目前，设备跟踪所有维度方向变化的能力有限。
- **translation**：设备在所有维度上跟踪平移变化的功能目前受到限制。

## 与体积互动

- **onVolumeViewpointChange(updateStrategy:initial:_:)**：添加在体的视角发生变化时执行的操作。
- **supportedVolumeViewpoints(_:)**：指定卷中的窗口栏和装饰物支持哪些视点。
- **VolumeViewpointUpdateStrategy**：描述应在何时调用提供给 [onVolumeViewpointChange(updateStrategy:initial:_:)](View/onVolumeViewpointChange_updateStrategy_initial.zh-Hans.md) 的操作的类型。
- **Viewpoint3D**：描述从哪个方向观看某物的类型。
- **SquareAzimuth**：描述沿水平面从哪个方向观看某物的类型，并向 4 个方向折叠。
- **WorldAlignmentBehavior**：表示场景的世界对齐行为的类型。
- **volumeWorldAlignment(_:)**：指定体积在世界中移动时的对齐方式。
- **WorldScalingBehavior**：指定窗口在世界中的缩放行为。
- **defaultWorldScaling(_:)**：为窗口指定世界缩放行为。
- **WorldScalingCompensation**：表示返回的度量是否将动态缩放考虑在内。
- **worldTrackingLimitations**：设备跟踪用户周围环境的当前限制。
- **SurfaceSnappingInfo**：表示窗口场景快照状态信息的类型。

## 符合

- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/WorldTrackingLimitation
crawled: 2025-12-02T17:21:44Z
---

# WorldTrackingLimitation

**Structure**

A structure to represent limitations of tracking the user’s surroundings.

## Declaration

```swift
struct WorldTrackingLimitation
```

## Overview

You receive a set of world tracking limitations when you read the [worldTrackingLimitations](EnvironmentValues/worldTrackingLimitations.zh-Hans.md) environment value. The value tells you which limitations the device currently is facing. If any of the limitations occur due to changing circumstances, e.g., the lighting, the set is updated accordingly. For example, the following [Text](Text.zh-Hans.md) view automatically updates when the world tracking limitations change:

```swift
@Environment(\.worldTrackingLimitations)
private var worldTrackingLimitations

var body: some View {
    Text("Can track translation?" + worldTrackingLimitations
        .contains(.translation) ? "No" : "Yes")
}
```

## Type Properties

- **orientation**: The device capabilities of tracking orientation changes in all dimensions are currently limited.
- **translation**: The device capabilities of tracking translation changes in all dimensions are currently limited.

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
- **SurfaceSnappingInfo**: A type representing information about the window scenes snap state.

## Conforms To

- Equatable
- Hashable
- Sendable
- SendableMetatype

