--- 来源：https://developer.apple.com/documentation/swiftui/view/drawinggroup(opaque:colormode:)

抓取时间：2025-12-03T06:32:45Z

---

# drawingGroup(opaque:colorMode:)

**实例方法**

在最终显示之前，将此视图的内容合成到屏幕外图像中。

## 声明

```swift
nonisolated func drawingGroup(opaque: Bool = false, colorMode: ColorRenderingMode = .nonLinear) -> some View

```

## 参数

- **opaque**：一个布尔值，指示图像是否不透明。默认值为 `false`；如果设置为 `true`，则图像的 alpha 通道必须为 `1`。

- **colorMode**：[ColorRenderingMode](../ColorRenderingMode.zh-Hans.md) 中定义的一种工作颜色空间和存储格式。默认值为 [nonLinear](../ColorRenderingMode/nonLinear.zh-Hans.md)。

## 返回值

一个视图，在显示之前将其内容合成到屏幕外图像中。

## 说明

`drawingGroup(opaque:colorMode:)` 修改器在渲染之前将视图子树展平为单个视图。

在下面的示例中，视图的内容被合成到单个位图；然后，该位图将代替视图显示：

```swift
VStack {
    ZStack {
        Text("DrawingGroup")
            .foregroundColor(.black)
            .padding(20)
            .background(Color.red)
        Text("DrawingGroup")
            .blur(radius: 2)
    }
    .font(.largeTitle)
    .compositingGroup()
    .opacity(1.0)
}
 .background(Color.white)
 .drawingGroup()
```

## 合成视图

- **blendMode(_:)**：设置此视图与重叠视图合成的混合模式。

- **compositingGroup()**：将此视图包装在合成组中。

- **BlendMode**：用于合成包含重叠内容的视图的模式。

- **ColorRenderingMode**：用于颜色合成操作的可用颜色空间集合。

- **CompositorContent**

- **CompositorContentBuilder**：用于合成 [CompositorContent](../CompositorContent.zh-Hans.md) 元素集合的结果构建器。

- **AnyCompositorContent**：已擦除的合成器内容类型。


---
source: https://developer.apple.com/documentation/swiftui/view/drawinggroup(opaque:colormode:)
crawled: 2025-12-03T06:32:45Z
---

# drawingGroup(opaque:colorMode:)

**Instance Method**

Composites this view’s contents into an offscreen image before final display.

## Declaration

```swift
nonisolated func drawingGroup(opaque: Bool = false, colorMode: ColorRenderingMode = .nonLinear) -> some View

```

## Parameters

- **opaque**: A Boolean value that indicates whether the image is opaque. The default is `false`; if set to `true`, the alpha channel of the image must be `1`.
- **colorMode**: One of the working color space and storage formats defined in [ColorRenderingMode](../ColorRenderingMode.zh-Hans.md). The default is [nonLinear](../ColorRenderingMode/nonLinear.zh-Hans.md).

## Return Value

A view that composites this view’s contents into an offscreen image before display.

## Discussion

The `drawingGroup(opaque:colorMode:)` modifier flattens a subtree of views into a single view before rendering it.

In the example below, the contents of the view are composited to a single bitmap; the bitmap is then displayed in place of the view:

```swift
VStack {
    ZStack {
        Text("DrawingGroup")
            .foregroundColor(.black)
            .padding(20)
            .background(Color.red)
        Text("DrawingGroup")
            .blur(radius: 2)
    }
    .font(.largeTitle)
    .compositingGroup()
    .opacity(1.0)
}
 .background(Color.white)
 .drawingGroup()
```





## Compositing views

- **blendMode(_:)**: Sets the blend mode for compositing this view with overlapping views.
- **compositingGroup()**: Wraps this view in a compositing group.
- **BlendMode**: Modes for compositing a view with overlapping content.
- **ColorRenderingMode**: The set of possible working color spaces for color-compositing operations.
- **CompositorContent**
- **CompositorContentBuilder**: A result builder for composing a collection of [CompositorContent](../CompositorContent.zh-Hans.md) elements.
- **AnyCompositorContent**: Type erased compositor content.

