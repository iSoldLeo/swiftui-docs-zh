--- 来源：https://developer.apple.com/documentation/SwiftUI/Scene/defaultWorldScaling(_:)

抓取时间：2025-12-02T17:21:42Z

---

# defaultWorldScaling(_:)

**实例方法**

指定窗口的世界缩放行为。

## 声明

```swift
nonisolated func defaultWorldScaling(_ scaling: WorldScalingBehavior) -> some Scene

```

## 讨论

默认情况下，普通窗口会随着距离的增加而增大其物理尺寸，以确保它们保持相同的角度大小。这保证了文本和控件的清晰度和易用性。体积以固定的物理尺寸渲染，因为它们最常用于需要更高物理精度的 3D 内容。

此修饰符会覆盖体积的物理缩放行为，使其像窗口一样缩放，同时保持其他体积行为。

此修饰符对沉浸式空间或窗口样式不为 [volumetric](../WindowStyle/volumetric.zh-Hans.md) 的窗口无效。

```swift
@main
struct SampleApp: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
        }
        .windowStyle(.volumetric)
        .defaultWorldScaling(.dynamic)
    }
}
```

更多信息，请参阅《人机界面指南》中的 [doc://com.apple.documentation/design/Human-Interface-Guidelines/spatial-layout#Scale]。

## 与体交互

- **onVolumeViewpointChange(updateStrategy:initial:_:)**：添加一个在体视点改变时执行的操作。

- **supportedVolumeViewpoints(_:)**：指定体中窗口栏和装饰物支持的视点。

- **VolumeViewpointUpdateStrategy**：描述何时调用提供给 [onVolumeViewpointChange(updateStrategy:initial:_:)](../View/onVolumeViewpointChange_updateStrategy_initial.zh-Hans.md) 的操作的类型。

- **Viewpoint3D**：描述当前观察方向的类型。

- **SquareAzimuth**：描述物体在水平面上的观察方向，并吸附到四个方向的类型。

- **WorldAlignmentBehavior**：表示场景的世界对齐行为的类型。

- **volumeWorldAlignment(_:)**：指定物体在世界中移动时应如何对齐。

- **WorldScalingBehavior**：指定窗口在世界中的缩放行为。

- **WorldScalingCompensation**：指示返回的指标是否会考虑动态缩放。

- **worldTrackingLimitations**：设备当前跟踪用户周围环境的限制。

- **WorldTrackingLimitation**：表示跟踪用户周围环境限制的结构。

- **SurfaceSnappingInfo**：表示窗口场景吸附状态信息的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/Scene/defaultWorldScaling(_:)
crawled: 2025-12-02T17:21:42Z
---

# defaultWorldScaling(_:)

**Instance Method**

Specify the world scaling behavior for the window.

## Declaration

```swift
nonisolated func defaultWorldScaling(_ scaling: WorldScalingBehavior) -> some Scene

```

## Discussion

By default, regular windows increase their physical size as they move further away, ensuring they remain at the same angular size. This preserves legibility and ease of use for text and controls. Volumes render with a fixed physical size, because they are most commonly used for 3D content which is meant to behave with greater physical accuracy.

This modifier overrides the physical scaling behavior for volumes, so they scale like windows while still maintaining other volumetric behaviors.

This modifier has no effect on immersive spaces or windows without a window style of [volumetric](../WindowStyle/volumetric.zh-Hans.md).

```swift
@main
struct SampleApp: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
        }
        .windowStyle(.volumetric)
        .defaultWorldScaling(.dynamic)
    }
}
```

For further information, see [doc://com.apple.documentation/design/Human-Interface-Guidelines/spatial-layout#Scale] in the Human Interface Guidelines.

## Interacting with volumes

- **onVolumeViewpointChange(updateStrategy:initial:_:)**: Adds an action to perform when the viewpoint of the volume changes.
- **supportedVolumeViewpoints(_:)**: Specifies which viewpoints are supported for the window bar and ornaments in a volume.
- **VolumeViewpointUpdateStrategy**: A type describing when the action provided to [onVolumeViewpointChange(updateStrategy:initial:_:)](../View/onVolumeViewpointChange_updateStrategy_initial.zh-Hans.md) should be called.
- **Viewpoint3D**: A type describing what direction something is being viewed from.
- **SquareAzimuth**: A type describing what direction something is being viewed from along the horizontal plane and snapped to 4 directions.
- **WorldAlignmentBehavior**: A type representing the world alignment behavior for a scene.
- **volumeWorldAlignment(_:)**: Specifies how a volume should be aligned when moved in the world.
- **WorldScalingBehavior**: Specifies the scaling behavior a window should have within the world.
- **WorldScalingCompensation**: Indicates whether returned metrics will take dynamic scaling into account.
- **worldTrackingLimitations**: The current limitations of the device tracking the user’s surroundings.
- **WorldTrackingLimitation**: A structure to represent limitations of tracking the user’s surroundings.
- **SurfaceSnappingInfo**: A type representing information about the window scenes snap state.

