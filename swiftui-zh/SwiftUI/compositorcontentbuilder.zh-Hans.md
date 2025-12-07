--- 来源：https://developer.apple.com/documentation/swiftui/compositorcontentbuilder

抓取时间：2025-12-03T06:32:48Z

---

# CompositorContentBuilder

**Structure**

用于组合元素集合的结果构建器。[CompositorContent](CompositorContent.zh-Hans.md)

## 声明

```swift
@resultBuilder struct CompositorContentBuilder
```

## 结构体

- **CompositorContentBuilder.Content**：组合器内容构建器的内容表示。

## 类型方法

- **buildBlock(_:)**

- **buildEither(first:)**：当条件为真时，为多语句闭包中的条件语句生成内容。

- **buildEither(second:)**：当条件为假时，为多语句闭包中的条件语句生成内容。

- **buildExpression(_:)**

- **buildLimitedAvailability(_:)**：处理执行可用性检查的条件编译器控制语句的场景内容。

## 合成视图

- **blendMode(_:)**：设置此视图与重叠视图合成的混合模式。

- **compositingGroup()**：将此视图包装在合成组中。

- **drawingGroup(opaque:colorMode:)**：在最终显示之前，将此视图的内容合成到屏幕外图像中。

- **BlendMode**：用于将视图与重叠内容合成的模式。

- **ColorRenderingMode**：用于颜色合成操作的可用颜色空间集合。

- **CompositorContent**

- **AnyCompositorContent**：已擦除的合成器内容类型。


---
source: https://developer.apple.com/documentation/swiftui/compositorcontentbuilder
crawled: 2025-12-03T06:32:48Z
---

# CompositorContentBuilder

**Structure**

A result builder for composing a collection of [CompositorContent](CompositorContent.zh-Hans.md) elements.

## Declaration

```swift
@resultBuilder struct CompositorContentBuilder
```

## Structures

- **CompositorContentBuilder.Content**: A representation of the content of a compositor content builder.

## Type Methods

- **buildBlock(_:)**
- **buildEither(first:)**: Produces content for a conditional statement in a multi-statement closure when the condition is true.
- **buildEither(second:)**: Produces content for a conditional statement in a multi-statement closure when the condition is false.
- **buildExpression(_:)**
- **buildLimitedAvailability(_:)**: Processes scene content for a conditional compiler-control statement that performs an availability check.

## Compositing views

- **blendMode(_:)**: Sets the blend mode for compositing this view with overlapping views.
- **compositingGroup()**: Wraps this view in a compositing group.
- **drawingGroup(opaque:colorMode:)**: Composites this view’s contents into an offscreen image before final display.
- **BlendMode**: Modes for compositing a view with overlapping content.
- **ColorRenderingMode**: The set of possible working color spaces for color-compositing operations.
- **CompositorContent**
- **AnyCompositorContent**: Type erased compositor content.

