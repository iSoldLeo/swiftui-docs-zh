--- 来源：https://developer.apple.com/documentation/SwiftUI/View/mapFeatureSelectionDisabled(_:)

抓取时间：2025-12-02T17:24:39Z

---

# mapFeatureSelectionDisabled(_:)

**实例方法**

指定哪些地图要素应禁用选择。

## 声明

```swift
@MainActor @preconcurrency func mapFeatureSelectionDisabled(_ selectionDisabled: @escaping (MapFeature) -> Bool) -> some View

```

## 参数

- **selectionDisabled**：确定是否应禁用给定地图要素的选择。

## 说明

`selectionDisabled` 参数接受一个闭包，该闭包将地图要素映射到布尔值。如果该闭包对给定的地图要素返回 true，则该地图要素将被视为不可选择。

## 获取位置信息

- **LocationButton**：一个用于授予一次性位置授权的 SwiftUI 按钮。

- **Map**：一个用于显示嵌入式地图界面的视图。

- **mapStyle(_:)**：指定要使用的地图样式。

- **mapScope(_:)**：创建一个 SwiftUI 用于将地图控件连接到关联地图的 mapScope。

- **mapFeatureSelectionAccessory(_:)**：指定要为 `MapFeature` 显示的选择附件。

- **mapFeatureSelectionContent(content:)**：指定当前选定要素的自定义显示方式。

- **mapControls(_:)**：将关联环境中的所有 `Map` 视图配置为具有标准大小和位置控件

- **mapControlVisibility(_:)**：将环境中的所有地图控件配置为具有指定的可见性

- **mapCameraKeyframeAnimator(trigger:keyframes:)**：当给定的触发值发生变化时，使用给定的关键帧为 `Map` 的摄像机添加动画。

- **lookAroundViewer(isPresented:scene:allowsNavigation:showsRoadLabels:pointsOfInterest:onDismiss:)**

- **lookAroundViewer(isPresented:initialScene:allowsNavigation:showsRoadLabels:pointsOfInterest:onDismiss:)**

- **onMapCameraChange(frequency:_:)**：当地图摄像机取景发生变化时执行操作

- **mapItemDetailPopover(isPresented:item:displaysMap:attachmentAnchor:)**：显示地图项目详细信息弹出窗口。

- **mapItemDetailPopover(isPresented:item:displaysMap:attachmentAnchor:arrowEdge:)**：显示地图项目详细信息弹出窗口。

- **mapItemDetailPopover(item:displaysMap:attachmentAnchor:)**：显示地图项目详情弹出窗口。


---
source: https://developer.apple.com/documentation/SwiftUI/View/mapFeatureSelectionDisabled(_:)
crawled: 2025-12-02T17:24:39Z
---

# mapFeatureSelectionDisabled(_:)

**Instance Method**

Specifies which map features should have selection disabled.

## Declaration

```swift
@MainActor @preconcurrency func mapFeatureSelectionDisabled(_ selectionDisabled: @escaping (MapFeature) -> Bool) -> some View

```

## Parameters

- **selectionDisabled**: Determines if selection should be disabled for a given map feature.

## Discussion

The `selectionDisabled` parameter takes a closure which maps map features, to booleans. If that closure returns true for a given map feature, that map feature will be considered unselectable.

## Getting location information

- **LocationButton**: A SwiftUI button that grants one-time location authorization.
- **Map**: A view that displays an embedded map interface.
- **mapStyle(_:)**: Specifies the map style to be used.
- **mapScope(_:)**: Creates a mapScope that SwiftUI uses to connect map controls to an associated map.
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
- **mapItemDetailPopover(item:displaysMap:attachmentAnchor:)**: Presents a map item detail popover.

