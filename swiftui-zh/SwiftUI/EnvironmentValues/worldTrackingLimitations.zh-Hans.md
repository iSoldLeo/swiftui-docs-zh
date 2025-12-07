---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/worldTrackingLimitations
抓取时间： 2025-12-02T17:21:43Z
---

# 世界追踪限制

**实例属性**

追踪用户周围环境的设备的当前限制。

## 声明

```swift
var worldTrackingLimitations: Set<WorldTrackingLimitation> { get set }
```

## 讨论

从视图中读取此环境值，可获得设备跟踪用户周围环境的当前限制。设备的功能可能会因照明等物理环境而受到限制。如果由于环境变化而出现任何限制，则会相应地更新设置。例如，当世界追踪限制发生变化时，下面的[Text](../Text.zh-Hans.md)视图会自动更新：

```swift
@Environment(\.worldTrackingLimitations)
private var worldTrackingLimitations

var body: some View {
    Text("Can track translation?" + worldTrackingLimitations
        .contains(.translation) ? "No" : "Yes")
}
```

当设备的世界跟踪功能受到限制时，不要完全阻止用户体验您的应用。相反，请尽量根据当前情况调整用户体验，以便随时提供有意义的体验。

##与体积互动

- **onVolumeViewpointChange(updateStrategy:initial:_:)**：当音量的视角发生变化时，添加一个要执行的操作。
- **supportedVolumeViewpoints(_:)**：指定卷中的窗口栏和装饰物支持哪些视点。
- **VolumeViewpointUpdateStrategy**：描述何时应调用提供给 [onVolumeViewpointChange(updateStrategy:initial:_:)](../View/onVolumeViewpointChange_updateStrategy_initial.zh-Hans.md) 的操作的类型。
- **Viewpoint3D**：描述从哪个方向观看某物的类型。
- **SquareAzimuth**：描述沿水平面从哪个方向观看某物的类型，并向 4 个方向折叠。
- **WorldAlignmentBehavior**：表示场景的世界对齐行为的类型。
- **volumeWorldAlignment(_:)**：指定体积在世界中移动时的对齐方式。
- **WorldScalingBehavior**：指定窗口在世界中的缩放行为。
- **defaultWorldScaling(_:)**：为窗口指定世界缩放行为。
- **WorldScalingCompensation**：表示返回的度量是否将动态缩放考虑在内。
- **WorldTrackingLimitation**：表示跟踪用户周围环境限制的结构。
- **SurfaceSnappingInfo**：表示窗口场景抓拍状态信息的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/worldTrackingLimitations
crawled: 2025-12-02T17:21:43Z
---

# worldTrackingLimitations

**Instance Property**

The current limitations of the device tracking the user’s surroundings.

## Declaration

```swift
var worldTrackingLimitations: Set<WorldTrackingLimitation> { get set }
```

## Discussion

Read this environment value from within a view to obtain the current limitations of the device tracking the user’s surroundings. The device’s capabilities may be limited due to physical circumstances such as the lighting. If any of the limitations occur due to changing circumstances, the set is updated accordingly. For example, the following [Text](../Text.zh-Hans.md) view automatically updates when the world tracking limitations change:

```swift
@Environment(\.worldTrackingLimitations)
private var worldTrackingLimitations

var body: some View {
    Text("Can track translation?" + worldTrackingLimitations
        .contains(.translation) ? "No" : "Yes")
}
```

When the device’s world tracking capabilities are limited, don’t prevent the user from experiencing your app entirely. Instead, try to adapt the user experience to the current circumstances in order to provide a meaningful experience at all times.

## Interacting with volumes

- **onVolumeViewpointChange(updateStrategy:initial:_:)**: Adds an action to perform when the viewpoint of the volume changes.
- **supportedVolumeViewpoints(_:)**: Specifies which viewpoints are supported for the window bar and ornaments in a volume.
- **VolumeViewpointUpdateStrategy**: A type describing when the action provided to [onVolumeViewpointChange(updateStrategy:initial:_:)](../View/onVolumeViewpointChange_updateStrategy_initial.zh-Hans.md) should be called.
- **Viewpoint3D**: A type describing what direction something is being viewed from.
- **SquareAzimuth**: A type describing what direction something is being viewed from along the horizontal plane and snapped to 4 directions.
- **WorldAlignmentBehavior**: A type representing the world alignment behavior for a scene.
- **volumeWorldAlignment(_:)**: Specifies how a volume should be aligned when moved in the world.
- **WorldScalingBehavior**: Specifies the scaling behavior a window should have within the world.
- **defaultWorldScaling(_:)**: Specify the world scaling behavior for the window.
- **WorldScalingCompensation**: Indicates whether returned metrics will take dynamic scaling into account.
- **WorldTrackingLimitation**: A structure to represent limitations of tracking the user’s surroundings.
- **SurfaceSnappingInfo**: A type representing information about the window scenes snap state.

