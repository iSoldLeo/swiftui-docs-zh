---
来源： https://developer.apple.com/documentation/swiftui/compositorcontent
抓取时间： 2025-12-03T06:32:54Z
---

# CompositorContent | 苹果开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ CompositorContent ](/documentation/swiftui/compositorcontent)

- 编辑器内容

协议# CompositorContent

macOS 26.0+visionOS 26.0+

```
@MainActor
protocol CompositorContent
```

## [主题](/documentation/swiftui/compositorcontent#topics)

### [关联类型](/documentation/swiftui/compositorcontent#Associated-Types)

[`associatedtype Body : CompositorContent`](/documentation/swiftui/compositorcontent/body-swift.associatedtype)**Required**

###[实例属性](/documentation/swiftui/compositorcontent#Instance-Properties)

[`var body: Self.Body`](/documentation/swiftui/compositorcontent/body-swift.property)**Required**

###[实例方法](/documentation/swiftui/compositorcontent#Instance-Methods)

[`func contentCaptureProtected(Bool) -> some CompositorContent`](/documentation/swiftui/compositorcontent/contentcaptureprotected(_:))将视图标记为在屏幕截图、屏幕录制、屏幕共享等场景捕获事件中激活内容保护的视图。[`func onAppear(perform: (() -> Void)?) -> some CompositorContent`](/documentation/swiftui/compositorcontent/onappear(perform:))添加要在该内容出现前执行的操作。[`func onChange(of:initial:_:)`](/documentation/swiftui/compositorcontent/onchange(of:initial:_:))[`func onDisappear(perform: (() -> Void)?) -> some CompositorContent`](/documentation/swiftui/compositorcontent/ondisappear(perform:))Adds an action to perform after this content disappears.[`func onImmersionChange(initial: Bool, (ImmersionChangeContext, ImmersionChangeContext) -> Void) -> some CompositorContent`](/documentation/swiftui/compositorcontent/onimmersionchange(initial:_:))当应用程序的沉浸状态发生变化时执行一个动作。[`func onWorldRecenter(action:)`](/documentation/swiftui/compositorcontent/onworldrecenter(action:))添加使用数字表冠重新定位视图时执行的操作。[`func persistentSystemOverlays(Visibility) -> some CompositorContent`](/documentation/swiftui/compositorcontent/persistentsystemoverlays(_:))设置覆盖应用程序的非瞬时系统视图的首选可见性。[`func preferredSurroundingsEffect(SurroundingsEffect?) -> some CompositorContent`](/documentation/swiftui/compositorcontent/preferredsurroundingseffect(_:))为直通视频应用效果。[`func upperLimbVisibility(Visibility) -> some CompositorContent`](/documentation/swiftui/compositorcontent/upperlimbvisibility(_:))在呈现 [`ImmersiveSpace`](/documentation/swiftui/immersivespace) 场景时设置用户上肢的首选可见度。

### [符合类型](/documentation/swiftui/compositorcontent#conforming-types)

- [⟦ic_0013⟧](⟦lu_0039⟧)

- 当 `C` 符合 `CompositorContent` 时，[`CompositorContentBuilder.Content`](/documentation/swiftui/compositorcontentbuilder/content) 符合。

## [See Also](/documentation/swiftui/compositorcontent#see-also)

### [合成视图](/documentation/swiftui/compositorcontent#Compositing-views)

[`func blendMode(BlendMode) -> some View`](/documentation/swiftui/view/blendmode(_:))设置将此视图与重叠视图合成时的混合模式。[`func drawingGroup(opaque: Bool, colorMode: ColorRenderingMode) -> some View`](/documentation/swiftui/view/drawinggroup(opaque:colormode:))在最终显示前将此视图的内容合成为离屏图像。 [`enum BlendMode`](/documentation/swiftui/blendmode)用于合成有重叠内容的视图的模式。[`enum ColorRenderingMode`](/documentation/swiftui/colorrenderingmode)用于色彩合成操作的可能工作色彩空间集。[`struct CompositorContentBuilder`](/documentation/swiftui/compositorcontentbuilder)用于合成 [`CompositorContent`](/documentation/swiftui/compositorcontent) 元素集合的结果生成器。[`struct AnyCompositorContent`](/documentation/swiftui/anycompositorcontent)类型擦除的合成器内容。

---
source: https://developer.apple.com/documentation/swiftui/compositorcontent
crawled: 2025-12-03T06:32:54Z
---

# CompositorContent | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ CompositorContent ](/documentation/swiftui/compositorcontent)

-  CompositorContent 

Protocol# CompositorContent

macOS 26.0+visionOS 26.0+

```
@MainActor
protocol CompositorContent
```

## [Topics](/documentation/swiftui/compositorcontent#topics)

### [Associated Types](/documentation/swiftui/compositorcontent#Associated-Types)

[`associatedtype Body : CompositorContent`](/documentation/swiftui/compositorcontent/body-swift.associatedtype)**Required**

### [Instance Properties](/documentation/swiftui/compositorcontent#Instance-Properties)

[`var body: Self.Body`](/documentation/swiftui/compositorcontent/body-swift.property)**Required**

### [Instance Methods](/documentation/swiftui/compositorcontent#Instance-Methods)

[`func contentCaptureProtected(Bool) -> some CompositorContent`](/documentation/swiftui/compositorcontent/contentcaptureprotected(_:))Marks the view as a view that activates content protection during scene capture events, such as screenshots, screen recordings, screensharing, etc.[`func onAppear(perform: (() -> Void)?) -> some CompositorContent`](/documentation/swiftui/compositorcontent/onappear(perform:))Adds an action to perform before this content appears.[`func onChange(of:initial:_:)`](/documentation/swiftui/compositorcontent/onchange(of:initial:_:))[`func onDisappear(perform: (() -> Void)?) -> some CompositorContent`](/documentation/swiftui/compositorcontent/ondisappear(perform:))Adds an action to perform after this content disappears.[`func onImmersionChange(initial: Bool, (ImmersionChangeContext, ImmersionChangeContext) -> Void) -> some CompositorContent`](/documentation/swiftui/compositorcontent/onimmersionchange(initial:_:))Performs an action when the immersion state of your app changes.[`func onWorldRecenter(action:)`](/documentation/swiftui/compositorcontent/onworldrecenter(action:))Adds an action to perform when recentering the view with the digital crown.[`func persistentSystemOverlays(Visibility) -> some CompositorContent`](/documentation/swiftui/compositorcontent/persistentsystemoverlays(_:))Sets the preferred visibility of the non-transient system views overlaying the app.[`func preferredSurroundingsEffect(SurroundingsEffect?) -> some CompositorContent`](/documentation/swiftui/compositorcontent/preferredsurroundingseffect(_:))Applies an effect to passthrough video.[`func upperLimbVisibility(Visibility) -> some CompositorContent`](/documentation/swiftui/compositorcontent/upperlimbvisibility(_:))Sets the preferred visibility of the user’s upper limbs, while an [`ImmersiveSpace`](/documentation/swiftui/immersivespace) scene is presented.## [Relationships](/documentation/swiftui/compositorcontent#relationships)

### [Conforming Types](/documentation/swiftui/compositorcontent#conforming-types)

- [`AnyCompositorContent`](/documentation/swiftui/anycompositorcontent)

- [`CompositorContentBuilder.Content`](/documentation/swiftui/compositorcontentbuilder/content)Conforms when `C` conforms to `CompositorContent`.

## [See Also](/documentation/swiftui/compositorcontent#see-also)

### [Compositing views](/documentation/swiftui/compositorcontent#Compositing-views)

[`func blendMode(BlendMode) -> some View`](/documentation/swiftui/view/blendmode(_:))Sets the blend mode for compositing this view with overlapping views.[`func compositingGroup() -> some View`](/documentation/swiftui/view/compositinggroup())Wraps this view in a compositing group.[`func drawingGroup(opaque: Bool, colorMode: ColorRenderingMode) -> some View`](/documentation/swiftui/view/drawinggroup(opaque:colormode:))Composites this view’s contents into an offscreen image before final display.[`enum BlendMode`](/documentation/swiftui/blendmode)Modes for compositing a view with overlapping content.[`enum ColorRenderingMode`](/documentation/swiftui/colorrenderingmode)The set of possible working color spaces for color-compositing operations.[`struct CompositorContentBuilder`](/documentation/swiftui/compositorcontentbuilder)A result builder for composing a collection of [`CompositorContent`](/documentation/swiftui/compositorcontent) elements.[`struct AnyCompositorContent`](/documentation/swiftui/anycompositorcontent)Type erased compositor content.