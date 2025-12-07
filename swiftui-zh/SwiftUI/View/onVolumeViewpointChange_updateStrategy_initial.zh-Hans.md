--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onVolumeViewpointChange(updateStrategy:initial:_:)

抓取时间：2025-11-30T20:06:46Z

---

# onVolumeViewpointChange(updateStrategy:initial:_:)

**实例方法**

添加一个在音量视图视角改变时执行的操作。

## 声明

```swift
@MainActor @preconcurrency func onVolumeViewpointChange(updateStrategy: VolumeViewpointUpdateStrategy = .supported, initial: Bool = true, _ action: @escaping (Viewpoint3D, Viewpoint3D) -> Void) -> some View

```

## 参数

- **updateStrategy**：该操作是应该在所有视角改变时执行，还是仅在支持的视角改变时执行。

- **initial**：该操作是否应该在视图首次出现时执行。

- **action**：一个在视角改变时要执行的闭包。如果 `initial` 为 `true`，则在首次打开卷时也会运行闭包。

## 讨论

使用提供的 [Viewpoint3D](../Viewpoint3D.zh-Hans.md) 更新卷的内容：

```swift
struct RobotContentView: View {
    @State var robotRotation: Rotation3D = .identity

    var body: some View {
        Model3D(named: "robot")
            .onVolumeViewpointChange { _, newValue in
                robotRotation = Rotation3D.slerp(
                    from: robotRotation,
                    to: newValue.squareAzimuth.orientation,
                    t: 1.0,
                    along: .shortest
                )
            }
            .rotation3DEffect(robotRotation)
            .animation(.easeInOut, value: robotRotation)
    }
}
```

默认情况下，仅当新视点等于通过 [supportedVolumeViewpoints(_:)](supportedVolumeViewpoints.zh-Hans.md) 提供的值之一时，才会运行此操作。视点将等于卷的窗口栏和装饰条所在的位置。如果为 `updateStrategy` 参数提供 `.all`，则调用此操作时将忽略支持的视点。

要确定是否从不支持的视点查看体，请为参数 `updateStrategy` 提供 `.all`，并检查该视点是否不在支持的视点范围内：

```swift
struct ContentView: View {
    @State var showingMoveToFrontSign = false
    @State var moveToFrontSignViewpoint: Viewpoint3D = .standard

    let supportedViewpoints = [SquareAzimuth.front]

    var body: some View {
        MoveToFrontSignView(viewpoint: moveToFrontSignViewpoint)
            .opacity(showingMoveToFrontSign ? 1.0 : 0.0)
            .animation(.easeInOut, value: showingMoveToFrontSign)
            .onVolumeViewpointChange(updateStrategy: .all)
                { _, newValue in

                moveToFrontSignViewpoint = newViewpoint

                let isSupported = supportedViewpoints.contains(
                    newViewpoint.squareAzimuth)
                showingMoveToFrontSign = !isSupported
            }
            .supportedVolumeViewpoints(supportedViewpoints)
    }
}
```

提供给操作的旧 [Viewpoint3D](../Viewpoint3D.zh-Hans.md) 和新 [Viewpoint3D](../Viewpoint3D.zh-Hans.md) 是相对于体的中心而言的。

读取此值仅在继承了使用 [VolumetricWindowStyle](../VolumetricWindowStyle.zh-Hans.md) 创建的 [Scene](../Scene.zh-Hans.md) 环境的 [View](../View.zh-Hans.md) 中有效。

## 与体交互

- **supportedVolumeViewpoints(_:)**：指定体中窗口栏和装饰物支持的视点。

- **VolumeViewpointUpdateStrategy**：描述何时调用提供给 [onVolumeViewpointChange(updateStrategy:initial:_:)](onVolumeViewpointChange_updateStrategy_initial.zh-Hans.md) 的动作的类型。

- **Viewpoint3D**：描述观察方向的类型。

- **SquareAzimuth**：描述沿水平面观察方向的类型，并捕捉到四个方向。

- **WorldAlignmentBehavior**：表示场景的世界对齐行为的类型。

- **volumeWorldAlignment(_:)**：指定在世界中移动时体积的对齐方式。

- **WorldScalingBehavior**：指定窗口在世界中的缩放行为。

- **defaultWorldScaling(_:)**：指定窗口的世界缩放行为。

- **WorldScalingCompensation**：指示返回的指标是否会考虑动态缩放。

- **worldTrackingLimitations**：设备当前跟踪用户周围环境的限制。

- **WorldTrackingLimitation**：用于表示跟踪用户周围环境限制的结构体。

- **SurfaceSnappingInfo**：表示窗口场景捕捉状态信息的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/View/onVolumeViewpointChange(updateStrategy:initial:_:)
crawled: 2025-11-30T20:06:46Z
---

# onVolumeViewpointChange(updateStrategy:initial:_:)

**Instance Method**

Adds an action to perform when the viewpoint of the volume changes.

## Declaration

```swift
@MainActor @preconcurrency func onVolumeViewpointChange(updateStrategy: VolumeViewpointUpdateStrategy = .supported, initial: Bool = true, _ action: @escaping (Viewpoint3D, Viewpoint3D) -> Void) -> some View

```

## Parameters

- **updateStrategy**: Whether the action should be run for all viewpoint changes or only for supported viewpoint changes.
- **initial**: Whether the action should be run when this view initially appears.
- **action**: A closure to run when the viewpoint changes. The closure is also run when the volume is first opened if `initial` is `true`.

## Discussion

Use the provided [Viewpoint3D](../Viewpoint3D.zh-Hans.md) to update the content of the volume:

```swift
struct RobotContentView: View {
    @State var robotRotation: Rotation3D = .identity

    var body: some View {
        Model3D(named: "robot")
            .onVolumeViewpointChange { _, newValue in
                robotRotation = Rotation3D.slerp(
                    from: robotRotation,
                    to: newValue.squareAzimuth.orientation,
                    t: 1.0,
                    along: .shortest
                )
            }
            .rotation3DEffect(robotRotation)
            .animation(.easeInOut, value: robotRotation)
    }
}
```

By default, the action will only be run when the new viewpoint is equivalent to one of the values provided through [supportedVolumeViewpoints(_:)](supportedVolumeViewpoints.zh-Hans.md). The viewpoint will be equivalent to where the window bar and ornaments are presented for a volume. Providing `.all` for the `updateStrategy` argument will result in the action being called without regard to the supported viewpoints.

To determine if the volume is being viewed from an unsupported viewpoint, provide `.all` for the `updateStrategy` argument and check if the viewpoint is not within the supported viewpoints:

```swift
struct ContentView: View {
    @State var showingMoveToFrontSign = false
    @State var moveToFrontSignViewpoint: Viewpoint3D = .standard

    let supportedViewpoints = [SquareAzimuth.front]

    var body: some View {
        MoveToFrontSignView(viewpoint: moveToFrontSignViewpoint)
            .opacity(showingMoveToFrontSign ? 1.0 : 0.0)
            .animation(.easeInOut, value: showingMoveToFrontSign)
            .onVolumeViewpointChange(updateStrategy: .all)
                { _, newValue in

                moveToFrontSignViewpoint = newViewpoint

                let isSupported = supportedViewpoints.contains(
                    newViewpoint.squareAzimuth)
                showingMoveToFrontSign = !isSupported
            }
            .supportedVolumeViewpoints(supportedViewpoints)
    }
}
```

The old and new [Viewpoint3D](../Viewpoint3D.zh-Hans.md) provided to the action are relative to the center of the volume.

Reading this value is only valid inside a [View](../View.zh-Hans.md) that inherits the environment of a [Scene](../Scene.zh-Hans.md) created with a [VolumetricWindowStyle](../VolumetricWindowStyle.zh-Hans.md).

## Interacting with volumes

- **supportedVolumeViewpoints(_:)**: Specifies which viewpoints are supported for the window bar and ornaments in a volume.
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

