---
来源：https://developer.apple.com/documentation/SwiftUI/GraphicsContext/clipToLayer(不透明度：选项：内容：)
抓取时间：2025-12-02T20:58:17Z
---

# clipToLayer(opacity:options:content:)

**实例方法**

将您在新图层中定义的剪辑形状添加到上下文的剪辑形状数组中。

## 声明

```swift
mutating func clipToLayer(opacity: Double = 1, options: GraphicsContext.ClipOptions = ClipOptions(), content: (inout GraphicsContext) throws -> Void) rethrows
```

## 参数

- **opacity**：SwiftUI 用来乘以您在`content` 闭合中定义的光栅化图层的 alpha 通道的值。由此产生的 alpha 值定义了剪辑形状。
- **options**：一组选项，用于告诉 SwiftUI 如何解释剪贴形状。例如，您可以通过设置[inverse](ClipOptions/inverse.zh-Hans.md) 选项来反转剪辑形状。
- **content**：一个闭包，它接收一个新的[GraphicsContext](../GraphicsContext.zh-Hans.md) 作为输入，新的[GraphicsContext](../GraphicsContext.zh-Hans.md) 表示一个新的透明度层。您在此上下文中绘制的内容的 alpha 通道乘以`opacity` 参数，就定义了剪辑的形状。

## 讨论

调用此方法可将一个形状添加到上下文用于定义剪切蒙版的剪辑形状数组中。添加的形状只影响后续的绘制操作。

## 遮罩

- **clip(to:style:options:)**：将路径添加到上下文的剪贴形状数组中。
- **clipBoundingRect**：当前用户空间中所有当前剪辑形状交集的边界矩形。
- **GraphicsContext.ClipOptions**：影响剪贴图形使用的选项。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/clipToLayer(opacity:options:content:)
crawled: 2025-12-02T20:58:17Z
---

# clipToLayer(opacity:options:content:)

**Instance Method**

Adds a clip shape that you define in a new layer to the context’s array of clip shapes.

## Declaration

```swift
mutating func clipToLayer(opacity: Double = 1, options: GraphicsContext.ClipOptions = ClipOptions(), content: (inout GraphicsContext) throws -> Void) rethrows
```

## Parameters

- **opacity**: A value that SwiftUI uses to multiply the alpha channel of the rasterized layer that you define in the `content` closure. The alpha values that result define the clip shape.
- **options**: A set of options that tell SwiftUI how to interpret the clip shape. For example, you can invert the clip shape by setting the [inverse](ClipOptions/inverse.zh-Hans.md) option.
- **content**: A closure that receives as input a new [GraphicsContext](../GraphicsContext.zh-Hans.md), which represents a new transparency layer. The alpha channel of content that you draw into this context, multiplied by the `opacity` parameter, defines the clip shape.

## Discussion

Call this method to add a shape to the array of clip shapes that the context uses to define a clipping mask. Shapes that you add affect only subsequent drawing operations.

## Masking

- **clip(to:style:options:)**: Adds a path to the context’s array of clip shapes.
- **clipBoundingRect**: The bounding rectangle of the intersection of all current clip shapes in the current user space.
- **GraphicsContext.ClipOptions**: Options that affect the use of clip shapes.

