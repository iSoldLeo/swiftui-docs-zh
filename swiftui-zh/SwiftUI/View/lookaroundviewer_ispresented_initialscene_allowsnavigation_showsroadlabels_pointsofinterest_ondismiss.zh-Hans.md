--- 来源：https://developer.apple.com/documentation/swiftui/view/lookaroundviewer(ispresented:initialscene:allowsnavigation:showsroadlabels:pointsofinterest:ondismiss:)

抓取时间：2025-12-03T05:36:55Z

---

# lookAroundViewer(isPresented:initialScene:allowsNavigation:showsRoadLabels:pointsOfInterest:onDismiss:) | Apple 开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ View ](/documentation/swiftui/view)

- [ lookAroundViewer(isPresented:initialScene:allowsNavigation:showsRoadLabels:pointsOfInterest:onDismiss:) ](/documentation/swiftui/view/lookaroundviewer(ispresented:initialscene:allowsnavigation:showsroadlabels:pointsofinterest:ondismiss:))

- [ View ](/documentation/swiftui/view)

- lookAroundViewer(isPresented:initialScene:allowsNavigation:showsRoadLabels:pointsOfInterest:onDismiss:) 

实例方法 # lookAroundViewer(isPresented:initialScene:allowsNavigation:showsRoadLabels:pointsOfInterest:onDismiss:)

MapKitSwiftUIiOS 17.0+iPadOS 17.0+

```
@MainActor @preconcurrency
func lookAroundViewer(
    isPresented: Binding<Bool>,
    initialScene: MKLookAroundScene?,
    allowsNavigation: Bool = true,
    showsRoadLabels: Bool = true,
    pointsOfInterest: PointOfInterestCategories = .all,
    onDismiss: (() -> Void)? = nil
) -> some View

```

## [另请参阅](/documentation/swiftui/view/lookaroundviewer(ispresented:initialscene:allowsnavigation:showsroadlabels:pointsofinterest:ondismiss:)#see-also)

### [获取位置信息](/documentation/swiftui/view/lookaroundviewer(ispresented:initialscene:allowsnavigation:showsroadlabels:pointsofinterest:ondismiss:)#Getting-location-information)

[`@MainActor @preconcurrency struct LocationButton`](/documentation/CoreLocationUI/LocationButton) 一个用于授予一次性位置授权的 SwiftUI 按钮。[`@MainActor @preconcurrency struct Map<Content> where Content : View`](/documentation/MapKit/Map) 显示嵌入式地图界面的视图。[`func mapStyle(MapStyle) -> some View`](/documentation/swiftui/view/mapstyle(_:) 指定要使用的地图样式。[`func mapScope(Namespace.ID) -> some View`](/documentation/swiftui/view/mapscope(_:) 创建一个 SwiftUI 用于将地图控件连接到关联视图的 mapScope。地图。[`func mapFeatureSelectionDisabled((MapFeature) -> Bool) -> some View`](/documentation/swiftui/view/mapfeatureselectiondisabled(_:))指定哪些地图要素应禁用选择。[`func mapFeatureSelectionAccessory(MapItemDetailSelectionAccessoryStyle?) -> some View`](/documentation/swiftui/view/mapfeatureselectionaccessory(_:))指定要为 `MapFeature` 显示的选择附件。[`func mapFeatureSelectionContent(content: (MapFeature) -> some MapContent) -> some View`](/documentation/swiftui/view/mapfeatureselectioncontent(content:))指定当前选定要素的自定义显示方式。[`func mapControls(() -> some View) -> some View`](/documentation/swiftui/view/mapcontrols(_:))配置关联环境中的所有视图，使其具有标准大小和位置控件。[`func mapControlVisibility(Visibility) -> some View`](/documentation/swiftui/view/mapcontrolvisibility(_:))配置环境中的所有地图控件，使其具有指定的控件。可见性[`func mapCameraKeyframeAnimator(trigger: some Equatable, keyframes: (MapCamera) -> some Keyframes<MapCamera>) -> some View`](/documentation/swiftui/view/mapcamerakeyframeanimator(trigger:keyframes:))当给定的触发值改变时，使用给定的关键帧为`Map`的摄像机添加动画。[`func lookAroundViewer(isPresented: Binding<Bool>, scene: Binding<MKLookAroundScene?>, allowsNavigation: Bool, showsRoadLabels: Bool, pointsOfInterest: PointOfInterestCategories, onDismiss: (() -> Void)?) -> some View`](/documentation/swiftui/view/lookaroundviewer(ispresented:scene:allowsnavigation:showsroadlabels:pointsofinterest:ondismiss:))[`func onMapCameraChange(frequency:_:)`](/documentation/swiftui/view/onmapcamerachange(frequency:_:))当地图摄像机取景改变时执行操作。[`func mapItemDetailPopover(isPresented: Binding<Bool>, item: MKMapItem?, displaysMap: Bool, attachmentAnchor: PopoverAttachmentAnchor) -> some View`](/documentation/swiftui/view/mapitemdetailpopover(ispresented:item:displaysmap:attachmentanchor:))显示地图项目详情弹出窗口。[`func mapItemDetailPopover(isPresented: Binding<Bool>, item: MKMapItem?, displaysMap: Bool, attachmentAnchor: PopoverAttachmentAnchor, arrowEdge: Edge) -> some View`](/documentation/swiftui/view/mapitemdetailpopover(ispresented:item:displaysmap:attachmentanchor:arrowedge:))显示地图项目详情popover.[`func mapItemDetailPopover(item: Binding<MKMapItem?>, displaysMap: Bool, attachmentAnchor: PopoverAttachmentAnchor) -> some View`](/documentation/swiftui/view/mapitemdetailpopover(item:displaysmap:attachmentanchor:))显示地图项目详细信息弹出窗口。

---
source: https://developer.apple.com/documentation/swiftui/view/lookaroundviewer(ispresented:initialscene:allowsnavigation:showsroadlabels:pointsofinterest:ondismiss:)
crawled: 2025-12-03T05:36:55Z
---

# lookAroundViewer(isPresented:initialScene:allowsNavigation:showsRoadLabels:pointsOfInterest:onDismiss:) | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ View ](/documentation/swiftui/view)

- [ lookAroundViewer(isPresented:initialScene:allowsNavigation:showsRoadLabels:pointsOfInterest:onDismiss:) ](/documentation/swiftui/view/lookaroundviewer(ispresented:initialscene:allowsnavigation:showsroadlabels:pointsofinterest:ondismiss:))

- [ View ](/documentation/swiftui/view)

-  lookAroundViewer(isPresented:initialScene:allowsNavigation:showsRoadLabels:pointsOfInterest:onDismiss:) 

Instance Method# lookAroundViewer(isPresented:initialScene:allowsNavigation:showsRoadLabels:pointsOfInterest:onDismiss:)

MapKitSwiftUIiOS 17.0+iPadOS 17.0+

```
@MainActor @preconcurrency
func lookAroundViewer(
    isPresented: Binding<Bool>,
    initialScene: MKLookAroundScene?,
    allowsNavigation: Bool = true,
    showsRoadLabels: Bool = true,
    pointsOfInterest: PointOfInterestCategories = .all,
    onDismiss: (() -> Void)? = nil
) -> some View

```

## [See Also](/documentation/swiftui/view/lookaroundviewer(ispresented:initialscene:allowsnavigation:showsroadlabels:pointsofinterest:ondismiss:)#see-also)

### [Getting location information](/documentation/swiftui/view/lookaroundviewer(ispresented:initialscene:allowsnavigation:showsroadlabels:pointsofinterest:ondismiss:)#Getting-location-information)

[`@MainActor @preconcurrency struct LocationButton`](/documentation/CoreLocationUI/LocationButton)A SwiftUI button that grants one-time location authorization.[`@MainActor @preconcurrency struct Map<Content> where Content : View`](/documentation/MapKit/Map)A view that displays an embedded map interface.[`func mapStyle(MapStyle) -> some View`](/documentation/swiftui/view/mapstyle(_:))Specifies the map style to be used.[`func mapScope(Namespace.ID) -> some View`](/documentation/swiftui/view/mapscope(_:))Creates a mapScope that SwiftUI uses to connect map controls to an associated map.[`func mapFeatureSelectionDisabled((MapFeature) -> Bool) -> some View`](/documentation/swiftui/view/mapfeatureselectiondisabled(_:))Specifies which map features should have selection disabled.[`func mapFeatureSelectionAccessory(MapItemDetailSelectionAccessoryStyle?) -> some View`](/documentation/swiftui/view/mapfeatureselectionaccessory(_:))Specifies the selection accessory to display for a `MapFeature`[`func mapFeatureSelectionContent(content: (MapFeature) -> some MapContent) -> some View`](/documentation/swiftui/view/mapfeatureselectioncontent(content:))Specifies a custom presentation for the currently selected feature.[`func mapControls(() -> some View) -> some View`](/documentation/swiftui/view/mapcontrols(_:))Configures all `Map` views in the associated environment to have standard size and position controls[`func mapControlVisibility(Visibility) -> some View`](/documentation/swiftui/view/mapcontrolvisibility(_:))Configures all Map controls in the environment to have the specified visibility[`func mapCameraKeyframeAnimator(trigger: some Equatable, keyframes: (MapCamera) -> some Keyframes<MapCamera>) -> some View`](/documentation/swiftui/view/mapcamerakeyframeanimator(trigger:keyframes:))Uses the given keyframes to animate the camera of a `Map` when the given trigger value changes.[`func lookAroundViewer(isPresented: Binding<Bool>, scene: Binding<MKLookAroundScene?>, allowsNavigation: Bool, showsRoadLabels: Bool, pointsOfInterest: PointOfInterestCategories, onDismiss: (() -> Void)?) -> some View`](/documentation/swiftui/view/lookaroundviewer(ispresented:scene:allowsnavigation:showsroadlabels:pointsofinterest:ondismiss:))[`func onMapCameraChange(frequency:_:)`](/documentation/swiftui/view/onmapcamerachange(frequency:_:))Performs an action when Map camera framing changes[`func mapItemDetailPopover(isPresented: Binding<Bool>, item: MKMapItem?, displaysMap: Bool, attachmentAnchor: PopoverAttachmentAnchor) -> some View`](/documentation/swiftui/view/mapitemdetailpopover(ispresented:item:displaysmap:attachmentanchor:))Presents a map item detail popover.[`func mapItemDetailPopover(isPresented: Binding<Bool>, item: MKMapItem?, displaysMap: Bool, attachmentAnchor: PopoverAttachmentAnchor, arrowEdge: Edge) -> some View`](/documentation/swiftui/view/mapitemdetailpopover(ispresented:item:displaysmap:attachmentanchor:arrowedge:))Presents a map item detail popover.[`func mapItemDetailPopover(item: Binding<MKMapItem?>, displaysMap: Bool, attachmentAnchor: PopoverAttachmentAnchor) -> some View`](/documentation/swiftui/view/mapitemdetailpopover(item:displaysmap:attachmentanchor:))Presents a map item detail popover.