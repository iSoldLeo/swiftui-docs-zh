--- 来源：https://developer.apple.com/documentation/swiftui/view/mapcontrolvisibility(_:)

抓取时间：2025-12-01T10:25:46Z

---

# mapControlVisibility(_:)

**实例方法**

配置环境中所有地图控件的可见性

## 声明

```swift
@MainActor @preconcurrency func mapControlVisibility(_ visibility: Visibility) -> some View

```

## 参数

- **visibility**：修改后的地图控件应如何显示或隐藏

## 讨论

MapCompass、MapScaleView 和 MapPitchToggle 可能会根据地图的当前状态自动显示和隐藏。但这可能不适用于所有用例，有时可能需要始终显示控件。

```swift
HStack {
    MapCompass()
    MapScaleView()
    MapPitchToggle()
}
.mapControls(.visible)
```

其他控件没有自动可见性行为，因此即使指定了 automatic，它们也将始终可见。当不适合对视图进行条件化时，也可以使用此修饰符隐藏控件。

```swift
MapUserLocationButton()
    .mapControls(.automatic)
MapZoomStepper()
    .mapControls(.hidden)
```

## 获取位置信息

- **LocationButton**：一个用于授予一次性位置授权的 SwiftUI 按钮。

- **Map**：一个显示嵌入式地图界面的视图。

- **mapStyle(_:)**：指定要使用的地图样式。

- **mapScope(_:)**：创建一个 SwiftUI 用于将地图控件连接到关联地图的 mapScope。

- **mapFeatureSelectionDisabled(_:)**：指定哪些地图要素应禁用选择。

- **mapFeatureSelectionAccessory(_:)**：指定要为 `MapFeature` 显示的选择附件。

- **mapFeatureSelectionContent(content:)**：指定当前选定要素的自定义显示方式。

- **mapControls(_:)**：将关联环境中的所有 `Map` 视图配置为具有标准大小和位置控件。

- **mapCameraKeyframeAnimator(trigger:keyframes:)**：当给定的触发值更改时，使用给定的关键帧为 `Map` 的摄像机添加动画。

- **lookAroundViewer(isPresented:scene:allowsNavigation:showsRoadLabels:pointsOfInterest:onDismiss:)**

- **lookAroundViewer(isPresented:initialScene:allowsNavigation:showsRoadLabels:pointsOfInterest:onDismiss:)**

- **onMapCameraChange(frequency:_:)**：在地图摄像机取景框更改时执行操作。

- **mapItemDetailPopover(isPresented:item:displaysMap:attachmentAnchor:)**：显示地图项目详细信息弹出窗口。

- **mapItemDetailPopover(isPresented:item:displaysMap:attachmentAnchor:arrowEdge:)**：显示地图项目详情弹出窗口。

- **mapItemDetailPopover(item:displaysMap:attachmentAnchor:)**：显示地图项目详情弹出窗口。


---
source: https://developer.apple.com/documentation/swiftui/view/mapcontrolvisibility(_:)
crawled: 2025-12-01T10:25:46Z
---

# mapControlVisibility(_:)

**Instance Method**

Configures all Map controls in the environment to have the specified visibility

## Declaration

```swift
@MainActor @preconcurrency func mapControlVisibility(_ visibility: Visibility) -> some View

```

## Parameters

- **visibility**: How modified map controls should show or hide

## Discussion

MapCompass, MapScaleView, and MapPitchToggle may automatically show and hide based on the current state of the Map. That may not be appropriate for all use cases, where always showing a control may be desirable.

```swift
HStack {
    MapCompass()
    MapScaleView()
    MapPitchToggle()
}
.mapControls(.visible)
```

Other controls don’t have an automatic visibility behavior, so they will always be visible when automatic is specified. Controls may also be hidden via this modifier when conditionalizing the view is not appropriate

```swift
MapUserLocationButton()
    .mapControls(.automatic)
MapZoomStepper()
    .mapControls(.hidden)
```

## Getting location information

- **LocationButton**: A SwiftUI button that grants one-time location authorization.
- **Map**: A view that displays an embedded map interface.
- **mapStyle(_:)**: Specifies the map style to be used.
- **mapScope(_:)**: Creates a mapScope that SwiftUI uses to connect map controls to an associated map.
- **mapFeatureSelectionDisabled(_:)**: Specifies which map features should have selection disabled.
- **mapFeatureSelectionAccessory(_:)**: Specifies the selection accessory to display for a `MapFeature`
- **mapFeatureSelectionContent(content:)**: Specifies a custom presentation for the currently selected feature.
- **mapControls(_:)**: Configures all `Map` views in the associated environment to have standard size and position controls
- **mapCameraKeyframeAnimator(trigger:keyframes:)**: Uses the given keyframes to animate the camera of a `Map` when the given trigger value changes.
- **lookAroundViewer(isPresented:scene:allowsNavigation:showsRoadLabels:pointsOfInterest:onDismiss:)**
- **lookAroundViewer(isPresented:initialScene:allowsNavigation:showsRoadLabels:pointsOfInterest:onDismiss:)**
- **onMapCameraChange(frequency:_:)**: Performs an action when Map camera framing changes
- **mapItemDetailPopover(isPresented:item:displaysMap:attachmentAnchor:)**: Presents a map item detail popover.
- **mapItemDetailPopover(isPresented:item:displaysMap:attachmentAnchor:arrowEdge:)**: Presents a map item detail popover.
- **mapItemDetailPopover(item:displaysMap:attachmentAnchor:)**: Presents a map item detail popover.

