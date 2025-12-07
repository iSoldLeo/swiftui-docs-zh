---
来源：https://developer.apple.com/documentation/SwiftUI/Canvas/init(opaque:colorMode:rendersAsynchronously:renderer:symbols:)
抓取时间：2025-12-01T00:42:07Z
---

# init(opaque:colorMode:rendersAsynchronously:renderer:symbols:)

**Initializer**

创建并配置画布，并为其提供可渲染的子视图。

## 声明

```swift
init(opaque: Bool = false, colorMode: ColorRenderingMode = .nonLinear, rendersAsynchronously: Bool = false, renderer: @escaping (inout GraphicsContext, CGSize) -> Void, @ViewBuilder symbols: () -> Symbols)
```

## 参数

- **opaque**：布尔值，表示画布是否完全不透明。将该值设置为 `true`可能会提高性能，但在上下文中绘制非不透明图像会产生未定义的结果。默认值为`false`。
- **colorMode**：画布的工作色彩空间和存储格式。默认为[nonLinear](../ColorRenderingMode/nonLinear.zh-Hans.md)。
- **rendersAsynchronously**：布尔值，表示画布是否可以异步向父视图显示其内容。默认值为 `false`。
- **renderer**：用于立即模式绘图的闭包。该闭包接收两个输入：一个用于发出绘制命令的上下文，以及一个代表画布当前大小的尺寸，用于自定义内容。画布在需要重绘内容时会调用呈现器。
- **symbols**：用于在绘制过程中将 SwiftUI 视图提供给画布使用的[ViewBuilder](../ViewBuilder.zh-Hans.md)。使用 `View/tag(_:)` 修饰符对每个视图进行唯一标记，以便您可以使用 [resolveSymbol(id:)](../GraphicsContext/resolveSymbol_id.zh-Hans.md) 方法在呈现器中找到它们。

## 讨论

此初始化器的行为与 [init(opaque:colorMode:rendersAsynchronously:renderer:)](init_opaque_colorMode_rendersAsynchronously_renderer.zh-Hans.md) 初始化器类似，只是您还提供了一个 SwiftUI 视图集合，供呈现器用作绘制元素。

SwiftUI 会存储您在`symbols` 视图创建器中指定的每个子视图的呈现版本，并将这些版本提供给画布。标记每个子视图，以便可以使用[resolveSymbol(id:)](../GraphicsContext/resolveSymbol_id.zh-Hans.md) 方法在呈现器中检索它。例如，您可以使用传入的子视图作为每个数据点的标记来创建散点图：

```swift
struct ScatterPlotView<Mark: View>: View {
    let rects: [CGRect]
    let mark: Mark

    enum SymbolID: Int {
        case mark
    }

    var body: some View {
        Canvas { context, size in
            if let mark = context.resolveSymbol(id: SymbolID.mark) {
                for rect in rects {
                    context.draw(mark, in: rect)
                }
            }
        } symbols: {
            mark.tag(SymbolID.mark)
        }
        .frame(width: 300, height: 200)
        .border(Color.blue)
    }
}
```

您可以将任何 SwiftUI 视图用于`mark` 输入：

```swift
ScatterPlotView(rects: rects, mark: Image(systemName: "circle"))
```

如果`rects` 输入包含 50 个随机排列的[doc://com.apple.documentation/documentation/CoreFoundation/CGRect] 实例，SwiftUI 会绘制这样的图：



符号输入与您绘制到画布上的所有其他元素一样，缺乏单独的可访问性和交互性，即使原始 SwiftUI 视图具有这些属性。不过，您可以为整个画布添加可访问性和交互性修改器。

## 创建画布

- **init(opaque:colorMode:rendersAsynchronously:renderer:)**：创建并配置画布。


---
source: https://developer.apple.com/documentation/SwiftUI/Canvas/init(opaque:colorMode:rendersAsynchronously:renderer:symbols:)
crawled: 2025-12-01T00:42:07Z
---

# init(opaque:colorMode:rendersAsynchronously:renderer:symbols:)

**Initializer**

Creates and configures a canvas that you supply with renderable child views.

## Declaration

```swift
init(opaque: Bool = false, colorMode: ColorRenderingMode = .nonLinear, rendersAsynchronously: Bool = false, renderer: @escaping (inout GraphicsContext, CGSize) -> Void, @ViewBuilder symbols: () -> Symbols)
```

## Parameters

- **opaque**: A Boolean that indicates whether the canvas is fully opaque. You might be able to improve performance by setting this value to `true`, but then drawing a non-opaque image into the context produces undefined results. The default is `false`.
- **colorMode**: A working color space and storage format of the canvas. The default is [nonLinear](../ColorRenderingMode/nonLinear.zh-Hans.md).
- **rendersAsynchronously**: A Boolean that indicates whether the canvas can present its contents to its parent view asynchronously. The default is `false`.
- **renderer**: A closure in which you conduct immediate mode drawing. The closure takes two inputs: a context that you use to issue drawing commands and a size — representing the current size of the canvas — that you can use to customize the content. The canvas calls the renderer any time it needs to redraw the content.
- **symbols**: A [ViewBuilder](../ViewBuilder.zh-Hans.md) that you use to supply SwiftUI views to the canvas for use during drawing. Uniquely tag each view using the `View/tag(_:)` modifier, so that you can find them from within your renderer using the [resolveSymbol(id:)](../GraphicsContext/resolveSymbol_id.zh-Hans.md) method.

## Discussion

This initializer behaves like the [init(opaque:colorMode:rendersAsynchronously:renderer:)](init_opaque_colorMode_rendersAsynchronously_renderer.zh-Hans.md) initializer, except that you also provide a collection of SwiftUI views for the renderer to use as drawing elements.

SwiftUI stores a rendered version of each child view that you specify in the `symbols` view builder and makes these available to the canvas. Tag each child view so that you can retrieve it from within the renderer using the [resolveSymbol(id:)](../GraphicsContext/resolveSymbol_id.zh-Hans.md) method. For example, you can create a scatter plot using a passed-in child view as the mark for each data point:

```swift
struct ScatterPlotView<Mark: View>: View {
    let rects: [CGRect]
    let mark: Mark

    enum SymbolID: Int {
        case mark
    }

    var body: some View {
        Canvas { context, size in
            if let mark = context.resolveSymbol(id: SymbolID.mark) {
                for rect in rects {
                    context.draw(mark, in: rect)
                }
            }
        } symbols: {
            mark.tag(SymbolID.mark)
        }
        .frame(width: 300, height: 200)
        .border(Color.blue)
    }
}
```

You can use any SwiftUI view for the `mark` input:

```swift
ScatterPlotView(rects: rects, mark: Image(systemName: "circle"))
```

If the `rects` input contains 50 randomly arranged [doc://com.apple.documentation/documentation/CoreFoundation/CGRect] instances, SwiftUI draws a plot like this:



The symbol inputs, like all other elements that you draw to the canvas, lack individual accessibility and interactivity, even if the original SwiftUI view has these attributes. However, you can add accessibility and interactivity modifers to the canvas as a whole.

## Creating a canvas

- **init(opaque:colorMode:rendersAsynchronously:renderer:)**: Creates and configures a canvas.

