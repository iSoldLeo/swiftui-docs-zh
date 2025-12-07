--- 来源：https://developer.apple.com/documentation/swiftui/view/mapcontrols(_:)

抓取时间：2025-12-03T05:36:38Z

---

# mapControls(_:)

**实例方法**

配置关联环境中所有视图，使其控件的大小和位置符合标准。

## 声明

```swift
@MainActor @preconcurrency func mapControls(@ViewBuilder _ content: () -> some View) -> some View

```

## 参数

- **content**：一个视图构建器，返回您希望在地图上显示的控件。

## 说明

您需要提供希望显示在地图顶部的控件。当控件与 `.mapControls` 结合使用时，无需指定作用域。非 MapKit 控件的视图将被忽略。

```swift
Map()
.mapControls {
    MapScaleView()
    MapUserLocationButton()
}
```

控件可以单独修改，也可以一次性全部修改。控件上设置的自定义边框和对齐方式将被忽略。

```swift
Map()
.mapControls {
    MapCompass()
        .mapControls(.visible)
    MapPitchToggle()
        .buttonBorderShape(.circular)
        .tint(.purple)
}
.controlSize(.large)
```

在 watchOS 上，空间非常宝贵。使用 mapControls 修饰符时，如果存在 MapUserLocationButton 和 MapCompass，则会自动合并。

```swift
Map()
.mapControls {
    MapUserLocationButton()
    MapCompass()
}
```

## 获取位置信息

- **LocationButton**：一个用于授予一次性位置授权的 SwiftUI 按钮。

- **Map**：一个显示嵌入式地图界面的视图。

- **mapStyle(_:)**：指定要使用的地图样式。

- **mapScope(_:)**：创建一个 mapScope，SwiftUI 使用该 mapScope 将地图控件连接到关联的地图。

- **mapFeatureSelectionDisabled(_:)**：指定哪些地图要素应禁用选择。

- **mapFeatureSelectionAccessory(_:)**：指定要为 `MapFeature` 显示的选择附件。

- **mapFeatureSelectionContent(content:)**：指定当前选定要素的自定义显示方式。

- **mapControlVisibility(_:)**：配置环境中所有地图控件的可见性。

- **mapCameraKeyframeAnimator(trigger:keyframes:)**：当给定的触发值发生变化时，使用给定的关键帧为 `Map` 的摄像机添加动画。

- **lookAroundViewer(isPresented:scene:allowsNavigation:showsRoadLabels:pointsOfInterest:onDismiss:)**

- **lookAroundViewer(isPresented:initialScene:allowsNavigation:showsRoadLabels:pointsOfInterest:onDismiss:)**

- **onMapCameraChange(frequency:_:)**：当地图相机取景框发生变化时执行操作

- **mapItemDetailPopover(isPresented:item:displaysMap:attachmentAnchor:)**：显示地图项目详情弹出窗口

- **mapItemDetailPopover(isPresented:item:displaysMap:attachmentAnchor:arrowEdge:)**：显示地图项目详情弹出窗口

- **mapItemDetailPopover(item:displaysMap:attachmentAnchor:)**：显示地图项目详情弹出窗口


---
source: https://developer.apple.com/documentation/swiftui/view/mapcontrols(_:)
crawled: 2025-12-03T05:36:38Z
---

# mapControls(_:)

**Instance Method**

Configures all `Map` views in the associated environment to have standard size and position controls

## Declaration

```swift
@MainActor @preconcurrency func mapControls(@ViewBuilder _ content: () -> some View) -> some View

```

## Parameters

- **content**: A view builder returning the controls you wish your `Map`

## Discussion

You provide the controls you want to appear atop your map. When using a control in conjunction with `.mapControls` you don’t need to specify a scope. Views that are not MapKit controls will be ignored.

```swift
Map()
.mapControls {
    MapScaleView()
    MapUserLocationButton()
}
```

Controls can be modified individually or all at once. Custom frames and alignments set on controls are ignored.

```swift
Map()
.mapControls {
    MapCompass()
        .mapControls(.visible)
    MapPitchToggle()
        .buttonBorderShape(.circular)
        .tint(.purple)
}
.controlSize(.large)
```

On watchOS, space is at a premium. When using the mapControls modifier, MapUserLocationButton and MapCompass are automatically combined if present.

```swift
Map()
.mapControls {
    MapUserLocationButton()
    MapCompass()
}
```

## Getting location information

- **LocationButton**: A SwiftUI button that grants one-time location authorization.
- **Map**: A view that displays an embedded map interface.
- **mapStyle(_:)**: Specifies the map style to be used.
- **mapScope(_:)**: Creates a mapScope that SwiftUI uses to connect map controls to an associated map.
- **mapFeatureSelectionDisabled(_:)**: Specifies which map features should have selection disabled.
- **mapFeatureSelectionAccessory(_:)**: Specifies the selection accessory to display for a `MapFeature`
- **mapFeatureSelectionContent(content:)**: Specifies a custom presentation for the currently selected feature.
- **mapControlVisibility(_:)**: Configures all Map controls in the environment to have the specified visibility
- **mapCameraKeyframeAnimator(trigger:keyframes:)**: Uses the given keyframes to animate the camera of a `Map` when the given trigger value changes.
- **lookAroundViewer(isPresented:scene:allowsNavigation:showsRoadLabels:pointsOfInterest:onDismiss:)**
- **lookAroundViewer(isPresented:initialScene:allowsNavigation:showsRoadLabels:pointsOfInterest:onDismiss:)**
- **onMapCameraChange(frequency:_:)**: Performs an action when Map camera framing changes
- **mapItemDetailPopover(isPresented:item:displaysMap:attachmentAnchor:)**: Presents a map item detail popover.
- **mapItemDetailPopover(isPresented:item:displaysMap:attachmentAnchor:arrowEdge:)**: Presents a map item detail popover.
- **mapItemDetailPopover(item:displaysMap:attachmentAnchor:)**: Presents a map item detail popover.

