--- 来源：https://developer.apple.com/documentation/swiftui/view/compositinggroup()

抓取时间：2025-12-01T11:21:55Z

---

# compositingGroup()

**实例方法**

将此视图包装在一个合成组中。

## 声明

```swift
nonisolated func compositingGroup() -> some View

```

## 返回值

一个将此视图包装在一个合成组中的视图。

## 说明

合成组使得此视图的父视图中的合成效果（例如不透明度和混合模式）在渲染此视图之前生效。

使用 `compositingGroup()` 可以在将效果应用于此视图之前，先将其应用于父视图。

在下面的示例中，`compositingGroup()` 修饰符将效果的应用分成多个阶段。它会在将 `blur(radius:)` 效果应用于封闭的 [ZStack](../ZStack.zh-Hans.md) 内的视图之前，先将 [opacity(_:)](opacity.zh-Hans.md) 效果应用于 VStack。这会将不透明度更改的范围限制在最外层的视图。

```swift
VStack {
    ZStack {
        Text("CompositingGroup")
            .foregroundColor(.black)
            .padding(20)
            .background(Color.red)
        Text("CompositingGroup")
            .blur(radius: 2)
    }
    .font(.largeTitle)
    .compositingGroup()
    .opacity(0.9)
}
```

## 合成视图

- **blendMode(_:)**：设置此视图与重叠视图合成的混合模式。

- **drawingGroup(opaque:colorMode:)**：在最终显示之前，将此视图的内容合成到屏幕外图像中。

- **BlendMode**：用于将视图与重叠内容合成的模式。

- **ColorRenderingMode**：用于颜色合成操作的可用颜色空间集。

- **CompositorContent**

- **CompositorContentBuilder**：用于组合 [CompositorContent](../CompositorContent.zh-Hans.md) 元素集合的结果构建器。

- **AnyCompositorContent**：类型擦除的合成器内容。


---
source: https://developer.apple.com/documentation/swiftui/view/compositinggroup()
crawled: 2025-12-01T11:21:55Z
---

# compositingGroup()

**Instance Method**

Wraps this view in a compositing group.

## Declaration

```swift
nonisolated func compositingGroup() -> some View

```

## Return Value

A view that wraps this view in a compositing group.

## Discussion

A compositing group makes compositing effects in this view’s ancestor views, such as opacity and the blend mode, take effect before this view is rendered.

Use `compositingGroup()` to apply effects to a parent view before applying effects to this view.

In the example below the `compositingGroup()` modifier separates the application of effects into stages. It applies the [opacity(_:)](opacity.zh-Hans.md) effect to the VStack before the `blur(radius:)` effect is applied to the views inside the enclosed [ZStack](../ZStack.zh-Hans.md). This limits the scope of the opacity change to the outermost view.

```swift
VStack {
    ZStack {
        Text("CompositingGroup")
            .foregroundColor(.black)
            .padding(20)
            .background(Color.red)
        Text("CompositingGroup")
            .blur(radius: 2)
    }
    .font(.largeTitle)
    .compositingGroup()
    .opacity(0.9)
}
```



## Compositing views

- **blendMode(_:)**: Sets the blend mode for compositing this view with overlapping views.
- **drawingGroup(opaque:colorMode:)**: Composites this view’s contents into an offscreen image before final display.
- **BlendMode**: Modes for compositing a view with overlapping content.
- **ColorRenderingMode**: The set of possible working color spaces for color-compositing operations.
- **CompositorContent**
- **CompositorContentBuilder**: A result builder for composing a collection of [CompositorContent](../CompositorContent.zh-Hans.md) elements.
- **AnyCompositorContent**: Type erased compositor content.

