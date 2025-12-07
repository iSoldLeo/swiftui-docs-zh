---
来源： https://developer.apple.com/documentation/swiftui/blendmode
抓取时间： 2025-12-03T06:32:46Z
---

# 混合模式

**Enumeration**

用于合成有重叠内容的视图的模式。

## 声明

```swift
enum BlendMode
```

## 获取默认值

- **BlendMode.normal**

## 变暗

- **BlendMode.darken**
- **BlendMode.multiply**
- **BlendMode.colorBurn**
- **BlendMode.plusDarker**

## Lightening

- **BlendMode.lighten**
- **BlendMode.screen**
- **BlendMode.colorDodge**
- **BlendMode.plusLighter**

## 增加对比度

- **BlendMode.overlay**
- **BlendMode.softLight**
- **BlendMode.hardLight**

## 反转

- **BlendMode.difference**
- **BlendMode.exclusion**

## 混合颜色成分

- **BlendMode.hue**
- **BlendMode.saturation**
- **BlendMode.color**
- **BlendMode.luminosity**

## 访问波特-达夫模式

- **BlendMode.sourceAtop**
- **BlendMode.destinationOver**
- **BlendMode.destinationOut**

## 合成视图

- **blendMode(_:)**：设置将此视图与重叠视图合成的混合模式。
- **compositingGroup()**：将此视图包裹在合成组中。
- **drawingGroup(opaque:colorMode:)**：在最终显示前将此视图的内容合成为屏幕外图像。
- **ColorRenderingMode**：用于色彩合成操作的可能工作色彩空间集。
- **CompositorContent**：用于色彩合成操作的可能工作色彩空间集。
- **CompositorContentBuilder**：[CompositorContent](CompositorContent.zh-Hans.md)元素集合的结果生成器。
- **AnyCompositorContent**：键入已删除的合成器内容。

## 符合

- 可复制
- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/swiftui/blendmode
crawled: 2025-12-03T06:32:46Z
---

# BlendMode

**Enumeration**

Modes for compositing a view with overlapping content.

## Declaration

```swift
enum BlendMode
```

## Getting the default

- **BlendMode.normal**

## Darkening

- **BlendMode.darken**
- **BlendMode.multiply**
- **BlendMode.colorBurn**
- **BlendMode.plusDarker**

## Lightening

- **BlendMode.lighten**
- **BlendMode.screen**
- **BlendMode.colorDodge**
- **BlendMode.plusLighter**

## Adding contrast

- **BlendMode.overlay**
- **BlendMode.softLight**
- **BlendMode.hardLight**

## Inverting

- **BlendMode.difference**
- **BlendMode.exclusion**

## Mixing color components

- **BlendMode.hue**
- **BlendMode.saturation**
- **BlendMode.color**
- **BlendMode.luminosity**

## Accessing porter-duff modes

- **BlendMode.sourceAtop**
- **BlendMode.destinationOver**
- **BlendMode.destinationOut**

## Compositing views

- **blendMode(_:)**: Sets the blend mode for compositing this view with overlapping views.
- **compositingGroup()**: Wraps this view in a compositing group.
- **drawingGroup(opaque:colorMode:)**: Composites this view’s contents into an offscreen image before final display.
- **ColorRenderingMode**: The set of possible working color spaces for color-compositing operations.
- **CompositorContent**
- **CompositorContentBuilder**: A result builder for composing a collection of [CompositorContent](CompositorContent.zh-Hans.md) elements.
- **AnyCompositorContent**: Type erased compositor content.

## Conforms To

- Copyable
- Equatable
- Hashable
- Sendable
- SendableMetatype

