--- 来源：https://developer.apple.com/documentation/swiftui/view/blendmode(_:)

抓取时间：2025-12-03T06:32:44Z

---

# blendMode(_:)

**实例方法**

设置此视图与重叠视图合成时的混合模式。

## 声明

```swift
nonisolated func blendMode(_ blendMode: BlendMode) -> some View

```

## 参数

- **blendMode**：用于合成此视图的 [BlendMode](../BlendMode.zh-Hans.md)。

## 返回值

一个应用 `blendMode` 的视图。

## 说明

使用 `blendMode(_:)` 组合重叠视图，并使用不同的视觉效果来生成结果。 [BlendMode](../BlendMode.zh-Hans.md) 枚举定义了许多可能的效果。

在下面的示例中，两个重叠的矩形应用了 [colorBurn](../BlendMode/colorBurn.zh-Hans.md) 效果，该效果有效地移除了第二个图像中不重叠的部分：

```swift
HStack {
    Color.yellow.frame(width: 50, height: 50, alignment: .center)

    Color.red.frame(width: 50, height: 50, alignment: .center)
        .rotationEffect(.degrees(45))
        .padding(-20)
        .blendMode(.colorBurn)
}
```

## 合成视图

- **compositingGroup()**：将此视图包装在合成组中。

- **drawingGroup(opaque:colorMode:)**：在最终显示之前，将此视图的内容合成到屏幕外图像中。

- **BlendMode**：用于合成具有重叠内容的视图的模式。

- **ColorRenderingMode**：用于颜色合成操作的可用工作颜色空间集。

- **CompositorContent**

- **CompositorContentBuilder**：用于组合 [CompositorContent](../CompositorContent.zh-Hans.md) 元素集合的结果构建器。

- **AnyCompositorContent**：类型擦除的合成器内容。


---
source: https://developer.apple.com/documentation/swiftui/view/blendmode(_:)
crawled: 2025-12-03T06:32:44Z
---

# blendMode(_:)

**Instance Method**

Sets the blend mode for compositing this view with overlapping views.

## Declaration

```swift
nonisolated func blendMode(_ blendMode: BlendMode) -> some View

```

## Parameters

- **blendMode**: The [BlendMode](../BlendMode.zh-Hans.md) for compositing this view.

## Return Value

A view that applies `blendMode` to this view.

## Discussion

Use `blendMode(_:)` to combine overlapping views and use a different visual effect to produce the result. The [BlendMode](../BlendMode.zh-Hans.md) enumeration defines many possible effects.

In the example below, the two overlapping rectangles have a [colorBurn](../BlendMode/colorBurn.zh-Hans.md) effect applied, which effectively removes the non-overlapping portion of the second image:

```swift
HStack {
    Color.yellow.frame(width: 50, height: 50, alignment: .center)

    Color.red.frame(width: 50, height: 50, alignment: .center)
        .rotationEffect(.degrees(45))
        .padding(-20)
        .blendMode(.colorBurn)
}
```



## Compositing views

- **compositingGroup()**: Wraps this view in a compositing group.
- **drawingGroup(opaque:colorMode:)**: Composites this view’s contents into an offscreen image before final display.
- **BlendMode**: Modes for compositing a view with overlapping content.
- **ColorRenderingMode**: The set of possible working color spaces for color-compositing operations.
- **CompositorContent**
- **CompositorContentBuilder**: A result builder for composing a collection of [CompositorContent](../CompositorContent.zh-Hans.md) elements.
- **AnyCompositorContent**: Type erased compositor content.

