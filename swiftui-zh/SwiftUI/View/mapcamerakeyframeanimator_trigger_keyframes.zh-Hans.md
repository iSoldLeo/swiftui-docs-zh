--- 来源：https://developer.apple.com/documentation/swiftui/view/mapcamerakeyframeanimator(trigger:keyframes:)

抓取时间：2025-12-01T10:25:47Z

---

# mapCameraKeyframeAnimator(trigger:keyframes:)

**实例方法**

当给定的触发值发生变化时，使用给定的关键帧为 `Map` 的摄像机添加动画。

## 声明

```swift
@MainActor @preconcurrency func mapCameraKeyframeAnimator(trigger: some Equatable, @KeyframesBuilder<MapCamera> keyframes: @escaping (MapCamera) -> some Keyframes<MapCamera>) -> some View

```

## 参数

- **trigger**：要观察其变化的值。

- **keyframes**：在开始新的关键帧动画时调用的关键帧构建器闭包。当前地图摄像机作为唯一参数提供。

## 讨论

当触发值发生变化时，地图会调用 `keyframes` 闭包来生成用于控制相机动画的关键帧。动画将持续您指定的关键帧时长。

如果用户在动画播放期间执行手势，动画将立即停止，从而允许交互控制相机。

## 获取位置信息

- **LocationButton**：一个用于授予一次性位置授权的 SwiftUI 按钮。

- **Map**：一个用于显示嵌入式地图界面的视图。

- **mapStyle(_:)**：指定要使用的地图样式。

- **mapScope(_:)**：创建一个 SwiftUI 用于将地图控件连接到关联地图的 mapScope。

- **mapFeatureSelectionDisabled(_:)**：指定哪些地图要素应禁用选择。

- **mapFeatureSelectionAccessory(_:)**：指定要为 `MapFeature` 显示的选择附件

- **mapFeatureSelectionContent(content:)**：指定当前选定要素的自定义显示方式

- **mapControls(_:)**：将关联环境中的所有 `Map` 视图配置为具有标准大小和位置控件

- **mapControlVisibility(_:)**：将环境中的所有地图控件配置为具有指定的可见性

- **lookAroundViewer(isPresented:scene:allowsNavigation:showsRoadLabels:pointsOfInterest:onDismiss:)**

- **lookAroundViewer(isPresented:initialScene:allowsNavigation:showsRoadLabels:pointsOfInterest:onDismiss:)**

- **onMapCameraChange(frequency:_:)**：在地图相机取景框更改时执行操作

- **mapItemDetailPopover(isPresented:item:displaysMap:attachmentAnchor:)**：显示地图项目详细信息弹出窗口

- **mapItemDetailPopover(isPresented:item:displaysMap:attachmentAnchor:arrowEdge:)**：显示地图项目详细信息弹出窗口- **mapItemDetailPopover(item:displaysMap:attachmentAnchor:)**：显示地图项目详情弹出窗口。


---
source: https://developer.apple.com/documentation/swiftui/view/mapcamerakeyframeanimator(trigger:keyframes:)
crawled: 2025-12-01T10:25:47Z
---

# mapCameraKeyframeAnimator(trigger:keyframes:)

**Instance Method**

Uses the given keyframes to animate the camera of a `Map` when the given trigger value changes.

## Declaration

```swift
@MainActor @preconcurrency func mapCameraKeyframeAnimator(trigger: some Equatable, @KeyframesBuilder<MapCamera> keyframes: @escaping (MapCamera) -> some Keyframes<MapCamera>) -> some View

```

## Parameters

- **trigger**: A value to observe for changes.
- **keyframes**: A keyframes builder closure that is called when starting a new keyframe animation. The current map camera is provided as the only parameter.

## Discussion

When the trigger value changes, the map calls the `keyframes` closure to generate the keyframes that will animate the camera. The animation will continue for the duration of the keyframes that you specify.

If the user performs a gesture while the animation is in progress, the animation will be immediately removed, allowing the interaction to take control of the camera.

## Getting location information

- **LocationButton**: A SwiftUI button that grants one-time location authorization.
- **Map**: A view that displays an embedded map interface.
- **mapStyle(_:)**: Specifies the map style to be used.
- **mapScope(_:)**: Creates a mapScope that SwiftUI uses to connect map controls to an associated map.
- **mapFeatureSelectionDisabled(_:)**: Specifies which map features should have selection disabled.
- **mapFeatureSelectionAccessory(_:)**: Specifies the selection accessory to display for a `MapFeature`
- **mapFeatureSelectionContent(content:)**: Specifies a custom presentation for the currently selected feature.
- **mapControls(_:)**: Configures all `Map` views in the associated environment to have standard size and position controls
- **mapControlVisibility(_:)**: Configures all Map controls in the environment to have the specified visibility
- **lookAroundViewer(isPresented:scene:allowsNavigation:showsRoadLabels:pointsOfInterest:onDismiss:)**
- **lookAroundViewer(isPresented:initialScene:allowsNavigation:showsRoadLabels:pointsOfInterest:onDismiss:)**
- **onMapCameraChange(frequency:_:)**: Performs an action when Map camera framing changes
- **mapItemDetailPopover(isPresented:item:displaysMap:attachmentAnchor:)**: Presents a map item detail popover.
- **mapItemDetailPopover(isPresented:item:displaysMap:attachmentAnchor:arrowEdge:)**: Presents a map item detail popover.
- **mapItemDetailPopover(item:displaysMap:attachmentAnchor:)**: Presents a map item detail popover.

