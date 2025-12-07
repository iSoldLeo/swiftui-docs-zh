--- 来源：https://developer.apple.com/documentation/SwiftUI/Scene/volumeWorldAlignment(_:)

抓取时间：2025-11-30T21:06:45Z

---

# volumeWorldAlignment(_:)

**实例方法**

指定体积在世界空间中移动时的对齐方式。

## 声明

```swift
nonisolated func volumeWorldAlignment(_ behavior: WorldAlignmentBehavior) -> some Scene

```

## 讨论

例如，您可以通过对场景应用 [gravityAligned](../WorldAlignmentBehavior/gravityAligned.zh-Hans.md) 对齐方式，创建一个即使被抬升到高于视线水平的高度也始终与地面平行的体积：

```swift
@main
struct MyApp: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
        }
        .windowStyle(.volumetric)
        .volumeWorldAlignment(.gravityAligned)
    }
}
```

如果不应用此修改器，则默认值为 [automatic](../WorldAlignmentBehavior/automatic.zh-Hans.md)。使用此方法，体积将自动倾斜，以便在重新定位时保持正面完全可见。

## 与体交互

- **onVolumeViewpointChange(updateStrategy:initial:_:)**：添加一个在体视点改变时执行的操作。

- **supportedVolumeViewpoints(_:)**：指定体中窗口栏和装饰物支持的视点。

- **VolumeViewpointUpdateStrategy**：描述何时调用提供给 [onVolumeViewpointChange(updateStrategy:initial:_:)](../View/onVolumeViewpointChange_updateStrategy_initial.zh-Hans.md) 的操作的类型。

- **Viewpoint3D**：描述观察方向的类型。

- **SquareAzimuth**：描述沿水平面观察方向的类型，并捕捉到四个方向。

- **WorldAlignmentBehavior**：表示场景的世界对齐行为的类型。

- **WorldScalingBehavior**：指定窗口在世界中的缩放行为。

- **defaultWorldScaling(_:)**：指定窗口的世界缩放行为。

- **WorldScalingCompensation**：指示返回的指标是否会考虑动态缩放。

- **worldTrackingLimitations**：设备当前跟踪用户周围环境的限制。

- **WorldTrackingLimitation**：用于表示跟踪用户周围环境限制的结构体。

- **SurfaceSnappingInfo**：表示窗口场景捕捉状态信息的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/Scene/volumeWorldAlignment(_:)
crawled: 2025-11-30T21:06:45Z
---

# volumeWorldAlignment(_:)

**Instance Method**

Specifies how a volume should be aligned when moved in the world.

## Declaration

```swift
nonisolated func volumeWorldAlignment(_ behavior: WorldAlignmentBehavior) -> some Scene

```

## Discussion

For example, you can create a volume that remains parallel to the floor even when lifted up high above eye level by applying a [gravityAligned](../WorldAlignmentBehavior/gravityAligned.zh-Hans.md) alignment to the scene:

```swift
@main
struct MyApp: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
        }
        .windowStyle(.volumetric)
        .volumeWorldAlignment(.gravityAligned)
    }
}
```

The default value if you don’t apply the modifier is [automatic](../WorldAlignmentBehavior/automatic.zh-Hans.md). With that strategy, volumes will tilt themselves so the front remains fully visible while being repositioned.

## Interacting with volumes

- **onVolumeViewpointChange(updateStrategy:initial:_:)**: Adds an action to perform when the viewpoint of the volume changes.
- **supportedVolumeViewpoints(_:)**: Specifies which viewpoints are supported for the window bar and ornaments in a volume.
- **VolumeViewpointUpdateStrategy**: A type describing when the action provided to [onVolumeViewpointChange(updateStrategy:initial:_:)](../View/onVolumeViewpointChange_updateStrategy_initial.zh-Hans.md) should be called.
- **Viewpoint3D**: A type describing what direction something is being viewed from.
- **SquareAzimuth**: A type describing what direction something is being viewed from along the horizontal plane and snapped to 4 directions.
- **WorldAlignmentBehavior**: A type representing the world alignment behavior for a scene.
- **WorldScalingBehavior**: Specifies the scaling behavior a window should have within the world.
- **defaultWorldScaling(_:)**: Specify the world scaling behavior for the window.
- **WorldScalingCompensation**: Indicates whether returned metrics will take dynamic scaling into account.
- **worldTrackingLimitations**: The current limitations of the device tracking the user’s surroundings.
- **WorldTrackingLimitation**: A structure to represent limitations of tracking the user’s surroundings.
- **SurfaceSnappingInfo**: A type representing information about the window scenes snap state.

