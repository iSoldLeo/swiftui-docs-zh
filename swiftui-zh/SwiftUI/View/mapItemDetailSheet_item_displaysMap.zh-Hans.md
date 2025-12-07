--- 来源：https://developer.apple.com/documentation/SwiftUI/View/mapItemDetailSheet(item:displaysMap:)

抓取时间：2025-11-30T21:09:48Z

---

# mapItemDetailSheet(item:displaysMap:)

**实例方法**

显示地图项详情页。

## 声明

```swift
@MainActor @preconcurrency func mapItemDetailSheet(item: Binding<MKMapItem?>, displaysMap: Bool = true) -> some View

```

## 参数

- **item**：当 `item` 不为 `nil` 时，显示地图项的详情页。

- **displaysMap**：是否应显示包含地点数据的内联地图。如果应用程序 UI 尚未在地图视图中显示该地点，则必须指定值 `true`。

## 获取位置信息

- **LocationButton**：一个授予一次性位置授权的 SwiftUI 按钮。

- **Map**：一个显示嵌入式地图界面的视图。

- **mapStyle(_:)**：指定要使用的地图样式。

- **mapScope(_:)**：创建一个 mapScope，SwiftUI 使用该 mapScope 将地图控件连接到关联的地图。

- **mapFeatureSelectionDisabled(_:)**：指定哪些地图要素应禁用选择。

- **mapFeatureSelectionAccessory(_:)**：指定要为 `MapFeature` 显示的选择附件。

- **mapFeatureSelectionContent(content:)**：指定当前选定要素的自定义显示方式。

- **mapControls(_:)**：将关联环境中的所有 `Map` 视图配置为具有标准大小和位置控件。

- **mapControlVisibility(_:)**：将环境中的所有地图控件配置为具有指定的可见性。

- **mapCameraKeyframeAnimator(trigger:keyframes:)**：当给定的触发值发生变化时，使用给定的关键帧为 `Map` 的摄像机添加动画。

- **lookAroundViewer(isPresented:scene:allowsNavigation:showsRoadLabels:pointsOfInterest:onDismiss:)**

- **lookAroundViewer(isPresented:initialScene:allowsNavigation:showsRoadLabels:pointsOfInterest:onDismiss:)**

- **onMapCameraChange(frequency:_:)**：当地图相机取景框发生变化时执行操作

- **mapItemDetailPopover(isPresented:item:displaysMap:attachmentAnchor:)**：显示地图项目详情弹出窗口

- **mapItemDetailPopover(isPresented:item:displaysMap:attachmentAnchor:arrowEdge:)**：显示地图项目详情弹出窗口


---
source: https://developer.apple.com/documentation/SwiftUI/View/mapItemDetailSheet(item:displaysMap:)
crawled: 2025-11-30T21:09:48Z
---

# mapItemDetailSheet(item:displaysMap:)

**Instance Method**

Presents a map item detail sheet.

## Declaration

```swift
@MainActor @preconcurrency func mapItemDetailSheet(item: Binding<MKMapItem?>, displaysMap: Bool = true) -> some View

```

## Parameters

- **item**: When `item` is non-`nil`, a detail sheet is displayed for the map item.
- **displaysMap**: If an inline map should be displayed with the place data. A value of `true` must be specified if the application UI is not already showing the place in a map view.

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
- **mapCameraKeyframeAnimator(trigger:keyframes:)**: Uses the given keyframes to animate the camera of a `Map` when the given trigger value changes.
- **lookAroundViewer(isPresented:scene:allowsNavigation:showsRoadLabels:pointsOfInterest:onDismiss:)**
- **lookAroundViewer(isPresented:initialScene:allowsNavigation:showsRoadLabels:pointsOfInterest:onDismiss:)**
- **onMapCameraChange(frequency:_:)**: Performs an action when Map camera framing changes
- **mapItemDetailPopover(isPresented:item:displaysMap:attachmentAnchor:)**: Presents a map item detail popover.
- **mapItemDetailPopover(isPresented:item:displaysMap:attachmentAnchor:arrowEdge:)**: Presents a map item detail popover.

