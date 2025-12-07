--- 来源：https://developer.apple.com/documentation/swiftui/anycompositorcontent

抓取时间：2025-12-03T06:32:42Z

---

# AnyCompositorContent

**Structure**

类型擦除合成器内容。

## 声明

```swift
struct AnyCompositorContent
```

## 初始化器

- **init(_:)**：创建一个实例，该实例会擦除 `CompositorContent` 的类型。

- **init(erasing:)**

## 合成视图

- **blendMode(_:)**：设置此视图与重叠视图合成的混合模式。

- **compositingGroup()**：将此视图包装在一个合成组中。

- **drawingGroup(opaque:colorMode:)**：在最终显示之前，将此视图的内容合成到屏幕外图像中。

- **BlendMode**：用于合成具有重叠内容的视图的模式。

- **ColorRenderingMode**：用于颜色合成操作的可用工作颜色空间集合。

- **CompositorContent**

- **CompositorContentBuilder**：用于合成 [CompositorContent](CompositorContent.zh-Hans.md) 元素集合的结果构建器。

## 符合以下规范

- CompositorContent


---
source: https://developer.apple.com/documentation/swiftui/anycompositorcontent
crawled: 2025-12-03T06:32:42Z
---

# AnyCompositorContent

**Structure**

Type erased compositor content.

## Declaration

```swift
struct AnyCompositorContent
```

## Initializers

- **init(_:)**: Create an instance that type-erases `CompositorContent`.
- **init(erasing:)**

## Compositing views

- **blendMode(_:)**: Sets the blend mode for compositing this view with overlapping views.
- **compositingGroup()**: Wraps this view in a compositing group.
- **drawingGroup(opaque:colorMode:)**: Composites this view’s contents into an offscreen image before final display.
- **BlendMode**: Modes for compositing a view with overlapping content.
- **ColorRenderingMode**: The set of possible working color spaces for color-compositing operations.
- **CompositorContent**
- **CompositorContentBuilder**: A result builder for composing a collection of [CompositorContent](CompositorContent.zh-Hans.md) elements.

## Conforms To

- CompositorContent

