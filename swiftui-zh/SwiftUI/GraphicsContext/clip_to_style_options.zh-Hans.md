---
来源：https://developer.apple.com/documentation/SwiftUI/GraphicsContext/clip(to:style:options:)
抓取时间： 2025-12-01T00:42:23Z
---

# clip(to:style:options:)

**实例方法**

将路径添加到上下文的剪辑形状数组中。

## 声明

```swift
mutating func clip(to path: Path, style: FillStyle = FillStyle(), options: GraphicsContext.ClipOptions = ClipOptions())
```

## 参数

- **path**：定义剪切蒙版形状的[Path](../Path.zh-Hans.md)。
- **style**：定义如何光栅化形状的[FillStyle](../FillStyle.zh-Hans.md)。
- **options**：剪贴选项，用于告诉 SwiftUI 如何将`path` 解释为剪贴形状。例如，您可以通过设置[inverse](ClipOptions/inverse.zh-Hans.md) 选项来反转剪辑形状。

## 讨论

调用此方法可将形状添加到上下文用来定义剪切蒙版的剪辑形状数组中。添加的形状只影响后续的绘制操作。

## 遮罩

- **clipToLayer(opacity:options:content:)**：将您在新图层中定义的剪贴形状添加到上下文的剪贴形状阵列中。
- **clipBoundingRect**：当前用户空间中所有当前剪辑形状交集的边界矩形。
- **GraphicsContext.ClipOptions**：影响剪贴图形使用的选项。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/clip(to:style:options:)
crawled: 2025-12-01T00:42:23Z
---

# clip(to:style:options:)

**Instance Method**

Adds a path to the context’s array of clip shapes.

## Declaration

```swift
mutating func clip(to path: Path, style: FillStyle = FillStyle(), options: GraphicsContext.ClipOptions = ClipOptions())
```

## Parameters

- **path**: A [Path](../Path.zh-Hans.md) that defines the shape of the clipping mask.
- **style**: A [FillStyle](../FillStyle.zh-Hans.md) that defines how to rasterize the shape.
- **options**: Clip options that tell SwiftUI how to interpret the `path` as a clip shape. For example, you can invert the clip shape by setting the [inverse](ClipOptions/inverse.zh-Hans.md) option.

## Discussion

Call this method to add a shape to the array of clip shapes that the context uses to define a clipping mask. Shapes that you add affect only subsequent drawing operations.

## Masking

- **clipToLayer(opacity:options:content:)**: Adds a clip shape that you define in a new layer to the context’s array of clip shapes.
- **clipBoundingRect**: The bounding rectangle of the intersection of all current clip shapes in the current user space.
- **GraphicsContext.ClipOptions**: Options that affect the use of clip shapes.

