---
来源： https://developer.apple.com/documentation/swiftui/environmentvalues/alloweddynamicrange
抓取时间： 2025-12-04T03:35:45Z
---

# allowedDynamicRange

**实例属性**

视图允许的动态范围，或为零。

## 声明

```swift
var allowedDynamicRange: Image.DynamicRange? { get set }
```

## 查看属性

- **backgroundMaterial**：当前视图下方的材质。
- **backgroundProminence**：与此环境相关的视图下方背景的突出度。
- **backgroundStyle**：可选样式，设置后会覆盖默认系统背景样式。
- **badgeProminence**：应用于与此环境关联的徽章的突出显示。
- **contentTransition**：当前为视图内容制作动画的方法。
- **contentTransitionAddsDrawingGroup**：一个布尔值，用于控制渲染内容转换的视图是否使用 GPU 加速渲染。
- **defaultMinListHeaderHeight**：列表中标题的默认最小高度。
- **defaultMinListRowHeight**：列表中标题的默认最小高度：列表中行的默认最小高度。
- **headerProminence**：视图中应用于章节标题的突出显示度。
- **physicalMetrics**：与场景相关联的物理度量。
- **realityKitScene**: 与场景相关的物理度量。
- **realityViewCameraControls**：现实视图的相机控件。
- **redactionReasons**：当前应用于视图层次结构的编辑原因。
- **springLoadingBehavior**：与此环境关联的视图的弹簧加载交互行为。
- **symbolRenderingMode**：当前的符号渲染模式，或 `nil`，表示使用当前图像和前景样式作为参数自动选择的模式。


---
source: https://developer.apple.com/documentation/swiftui/environmentvalues/alloweddynamicrange
crawled: 2025-12-04T03:35:45Z
---

# allowedDynamicRange

**Instance Property**

The allowed dynamic range for the view, or nil.

## Declaration

```swift
var allowedDynamicRange: Image.DynamicRange? { get set }
```

## View attributes

- **backgroundMaterial**: The material underneath the current view.
- **backgroundProminence**: The prominence of the background underneath views associated with this environment.
- **backgroundStyle**: An optional style that overrides the default system background style when set.
- **badgeProminence**: The prominence to apply to badges associated with this environment.
- **contentTransition**: The current method of animating the contents of views.
- **contentTransitionAddsDrawingGroup**: A Boolean value that controls whether views that render content transitions use GPU-accelerated rendering.
- **defaultMinListHeaderHeight**: The default minimum height of a header in a list.
- **defaultMinListRowHeight**: The default minimum height of rows in a list.
- **headerProminence**: The prominence to apply to section headers within a view.
- **physicalMetrics**: The physical metrics associated with a scene.
- **realityKitScene**
- **realityViewCameraControls**: The camera controls for the reality view.
- **redactionReasons**: The current redaction reasons applied to the view hierarchy.
- **springLoadingBehavior**: The behavior of spring loaded interactions for the views associated with this environment.
- **symbolRenderingMode**: The current symbol rendering mode, or `nil` denoting that the mode is picked automatically using the current image and foreground style as parameters.

