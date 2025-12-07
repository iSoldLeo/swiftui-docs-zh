---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/realityKitScene
抓取时间： 2025-12-03T06:07:28Z
---

# realityKitScene | 苹果开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ EnvironmentValues ](/documentation/swiftui/environmentvalues)

- [ realityKitScene ](/documentation/SwiftUI/EnvironmentValues/realityKitScene)

- [ 环境值 ](/documentation/swiftui/environmentvalues)

- 现实场景

实例属性# realityKitScene

RealityKitSwiftUIvisionOS 1.0+

```
var realityKitScene: Scene? { get }
```

## [See Also](/documentation/SwiftUI/EnvironmentValues/realityKitScene#see-also)

### [查看属性](/documentation/SwiftUI/EnvironmentValues/realityKitScene#View-attributes)

[`var allowedDynamicRange: Image.DynamicRange?`](/documentation/swiftui/environmentvalues/alloweddynamicrange)视图允许的动态范围，或为零。 [`var backgroundMaterial: Material?`](/documentation/swiftui/environmentvalues/backgroundmaterial)当前视图下方的材质。[`var backgroundProminence: BackgroundProminence`](/documentation/swiftui/environmentvalues/backgroundprominence)与此环境关联的视图下方背景的突出显示。 [`var backgroundStyle: AnyShapeStyle?`](/documentation/swiftui/environmentvalues/backgroundstyle)可选样式，设置后会覆盖默认的系统背景样式。[`var badgeProminence: BadgeProminence`](/documentation/swiftui/environmentvalues/badgeprominence)应用于与此环境相关联的徽章的显著性。[`var contentTransitionAddsDrawingGroup: Bool`](/documentation/swiftui/environmentvalues/contenttransitionaddsdrawinggroup)一个布尔值，用于控制渲染内容转换的视图是否使用 GPU 加速渲染。 [`var defaultMinListHeaderHeight: CGFloat?`](/documentation/swiftui/environmentvalues/defaultminlistheaderheight)列表中标题的默认最小高度。[`var defaultMinListRowHeight: CGFloat`](/documentation/swiftui/environmentvalues/defaultminlistrowheight)列表中行的默认最小高度。 [`var headerProminence: Prominence`](/documentation/swiftui/environmentvalues/headerprominence)视图中应用于章节标题的突出显示。[`var physicalMetrics: PhysicalMetricsConverter`](/documentation/swiftui/environmentvalues/physicalmetrics)与场景相关的物理指标。 [`var realityViewCameraControls: CameraControls`](/documentation/swiftui/environmentvalues/realityviewcameracontrols)现实视图的摄像机控件。[`var redactionReasons: RedactionReasons`](/documentation/swiftui/environmentvalues/redactionreasons)应用于视图层次结构的当前编辑原因。 [`var springLoadingBehavior: SpringLoadingBehavior`](/documentation/swiftui/environmentvalues/springloadingbehavior)与此环境相关的视图的弹簧加载交互行为。[`var symbolRenderingMode: SymbolRenderingMode?`](/documentation/swiftui/environmentvalues/symbolrenderingmode)当前的符号渲染模式，或`nil`表示使用当前图像和前景样式作为参数自动选择模式。

---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/realityKitScene
crawled: 2025-12-03T06:07:28Z
---

# realityKitScene | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ EnvironmentValues ](/documentation/swiftui/environmentvalues)

- [ realityKitScene ](/documentation/SwiftUI/EnvironmentValues/realityKitScene)

- [ EnvironmentValues ](/documentation/swiftui/environmentvalues)

-  realityKitScene 

Instance Property# realityKitScene

RealityKitSwiftUIvisionOS 1.0+

```
var realityKitScene: Scene? { get }
```

## [See Also](/documentation/SwiftUI/EnvironmentValues/realityKitScene#see-also)

### [View attributes](/documentation/SwiftUI/EnvironmentValues/realityKitScene#View-attributes)

[`var allowedDynamicRange: Image.DynamicRange?`](/documentation/swiftui/environmentvalues/alloweddynamicrange)The allowed dynamic range for the view, or nil.[`var backgroundMaterial: Material?`](/documentation/swiftui/environmentvalues/backgroundmaterial)The material underneath the current view.[`var backgroundProminence: BackgroundProminence`](/documentation/swiftui/environmentvalues/backgroundprominence)The prominence of the background underneath views associated with this environment.[`var backgroundStyle: AnyShapeStyle?`](/documentation/swiftui/environmentvalues/backgroundstyle)An optional style that overrides the default system background style when set.[`var badgeProminence: BadgeProminence`](/documentation/swiftui/environmentvalues/badgeprominence)The prominence to apply to badges associated with this environment.[`var contentTransition: ContentTransition`](/documentation/swiftui/environmentvalues/contenttransition)The current method of animating the contents of views.[`var contentTransitionAddsDrawingGroup: Bool`](/documentation/swiftui/environmentvalues/contenttransitionaddsdrawinggroup)A Boolean value that controls whether views that render content transitions use GPU-accelerated rendering.[`var defaultMinListHeaderHeight: CGFloat?`](/documentation/swiftui/environmentvalues/defaultminlistheaderheight)The default minimum height of a header in a list.[`var defaultMinListRowHeight: CGFloat`](/documentation/swiftui/environmentvalues/defaultminlistrowheight)The default minimum height of rows in a list.[`var headerProminence: Prominence`](/documentation/swiftui/environmentvalues/headerprominence)The prominence to apply to section headers within a view.[`var physicalMetrics: PhysicalMetricsConverter`](/documentation/swiftui/environmentvalues/physicalmetrics)The physical metrics associated with a scene.[`var realityViewCameraControls: CameraControls`](/documentation/swiftui/environmentvalues/realityviewcameracontrols)The camera controls for the reality view.[`var redactionReasons: RedactionReasons`](/documentation/swiftui/environmentvalues/redactionreasons)The current redaction reasons applied to the view hierarchy.[`var springLoadingBehavior: SpringLoadingBehavior`](/documentation/swiftui/environmentvalues/springloadingbehavior)The behavior of spring loaded interactions for the views associated with this environment.[`var symbolRenderingMode: SymbolRenderingMode?`](/documentation/swiftui/environmentvalues/symbolrenderingmode)The current symbol rendering mode, or `nil` denoting that the mode is picked automatically using the current image and foreground style as parameters.