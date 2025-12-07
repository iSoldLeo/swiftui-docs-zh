--- 来源：https://developer.apple.com/documentation/swiftui/view/mapfeatureselectioncontent(content:)

抓取时间：2025-12-03T05:36:37Z

---

# mapFeatureSelectionContent(content:)

**实例方法**

为当前选定的要素指定自定义显示方式。

## 声明

```swift
@MainActor @preconcurrency func mapFeatureSelectionContent(@MapContentBuilder content: @escaping (MapFeature) -> some MapContent) -> some View

```

## 参数

- **content**：为给定的地图要素生成自定义显示方式。

## 说明

支持的显示选项为 `Annotation` 和 `Marker`。其他类型的地图内容将被忽略，并视为未返回任何内容。

如果返回空地图内容，则将使用系统显示方式。

## 获取位置信息

- **LocationButton**：一个用于授予一次性位置授权的 SwiftUI 按钮。

- **Map**：一个用于显示嵌入式地图界面的视图。

- **mapStyle(_:)**：指定要使用的地图样式。

- **mapScope(_:)**：创建一个 SwiftUI 用于将地图控件连接到关联地图的 mapScope。

- **mapFeatureSelectionDisabled(_:)**：指定哪些地图要素应禁用选择。

- **mapFeatureSelectionAccessory(_:)**：指定要为 `MapFeature` 显示的选择附件

- **mapControls(_:)**：将关联环境中的所有 `Map` 视图配置为具有标准大小和位置控件

- **mapControlVisibility(_:)**：将环境中的所有地图控件配置为具有指定的可见性

- **mapCameraKeyframeAnimator(trigger:keyframes:)**：当给定的触发值更改时，使用给定的关键帧为 `Map` 的摄像机添加动画。

- **lookAroundViewer(isPresented:scene:allowsNavigation:showsRoadLabels:pointsOfInterest:onDismiss:)**

- **lookAroundViewer(isPresented:initialScene:allowsNavigation:showsRoadLabels:pointsOfInterest:onDismiss:)**

- **onMapCameraChange(frequency:_:)**：当地图摄像机取景更改时执行操作

- **mapItemDetailPopover(isPresented:item:displaysMap:attachmentAnchor:)**：显示地图项目详细信息弹出窗口。

- **mapItemDetailPopover(isPresented:item:displaysMap:attachmentAnchor:arrowEdge:)**：显示地图项目详情弹出窗口。

- **mapItemDetailPopover(item:displaysMap:attachmentAnchor:)**：显示地图项目详情弹出窗口。


---
source: https://developer.apple.com/documentation/swiftui/view/mapfeatureselectioncontent(content:)
crawled: 2025-12-03T05:36:37Z
---

# mapFeatureSelectionContent(content:)

**Instance Method**

Specifies a custom presentation for the currently selected feature.

## Declaration

```swift
@MainActor @preconcurrency func mapFeatureSelectionContent(@MapContentBuilder content: @escaping (MapFeature) -> some MapContent) -> some View

```

## Parameters

- **content**: Generates the custom presentation for a given map feature.

## Discussion

The supported presentation options are `Annotation`, and `Marker`. Other types of map content will be ignored and handled as though no content was returned.

If empty map content is returned, the system presentation will be used.

## Getting location information

- **LocationButton**: A SwiftUI button that grants one-time location authorization.
- **Map**: A view that displays an embedded map interface.
- **mapStyle(_:)**: Specifies the map style to be used.
- **mapScope(_:)**: Creates a mapScope that SwiftUI uses to connect map controls to an associated map.
- **mapFeatureSelectionDisabled(_:)**: Specifies which map features should have selection disabled.
- **mapFeatureSelectionAccessory(_:)**: Specifies the selection accessory to display for a `MapFeature`
- **mapControls(_:)**: Configures all `Map` views in the associated environment to have standard size and position controls
- **mapControlVisibility(_:)**: Configures all Map controls in the environment to have the specified visibility
- **mapCameraKeyframeAnimator(trigger:keyframes:)**: Uses the given keyframes to animate the camera of a `Map` when the given trigger value changes.
- **lookAroundViewer(isPresented:scene:allowsNavigation:showsRoadLabels:pointsOfInterest:onDismiss:)**
- **lookAroundViewer(isPresented:initialScene:allowsNavigation:showsRoadLabels:pointsOfInterest:onDismiss:)**
- **onMapCameraChange(frequency:_:)**: Performs an action when Map camera framing changes
- **mapItemDetailPopover(isPresented:item:displaysMap:attachmentAnchor:)**: Presents a map item detail popover.
- **mapItemDetailPopover(isPresented:item:displaysMap:attachmentAnchor:arrowEdge:)**: Presents a map item detail popover.
- **mapItemDetailPopover(item:displaysMap:attachmentAnchor:)**: Presents a map item detail popover.

