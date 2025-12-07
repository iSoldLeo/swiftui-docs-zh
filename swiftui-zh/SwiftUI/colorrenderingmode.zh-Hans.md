--- 来源：https://developer.apple.com/documentation/swiftui/colorrenderingmode
抓取时间：2025-12-03T06:32:47Z

---

# ColorRenderingMode

**Enumeration**

用于颜色合成操作的可用工作色彩空间集合。

## 声明

```swift
enum ColorRenderingMode
```

## 概述

每个色彩空间都保证保留特定范围内的颜色值。

## 获取渲染模式

- **ColorRenderingMode.extendedLinear**：扩展线性 sRGB 工作色彩空间。

- **ColorRenderingMode.linear**：线性 sRGB 工作色彩空间。

- **ColorRenderingMode.nonLinear**：非线性 sRGB 工作色彩空间。

## 合成视图

- **blendMode(_:)**：设置此视图与重叠视图合成的混合模式。

- **compositingGroup()**：将此视图包裹在合成组中。

- **drawingGroup(opaque:colorMode:)**：在最终显示之前，将此视图的内容合成到屏幕外图像中。

- **BlendMode**：用于合成包含重叠内容的视图的模式。

- **CompositorContent**

- **CompositorContentBuilder**：用于合成 [CompositorContent](CompositorContent.zh-Hans.md) 元素集合的结果构建器。

- **AnyCompositorContent**：类型擦除合成器内容。

## 符合以下标准

- 可复制

- 可等价比较

- 可哈希

- 可发送

- 可发送元数据


---
source: https://developer.apple.com/documentation/swiftui/colorrenderingmode
crawled: 2025-12-03T06:32:47Z
---

# ColorRenderingMode

**Enumeration**

The set of possible working color spaces for color-compositing operations.

## Declaration

```swift
enum ColorRenderingMode
```

## Overview

Each color space guarantees the preservation of a particular range of color values.

## Getting rendering modes

- **ColorRenderingMode.extendedLinear**: The extended linear sRGB working color space.
- **ColorRenderingMode.linear**: The linear sRGB working color space.
- **ColorRenderingMode.nonLinear**: The non-linear sRGB working color space.

## Compositing views

- **blendMode(_:)**: Sets the blend mode for compositing this view with overlapping views.
- **compositingGroup()**: Wraps this view in a compositing group.
- **drawingGroup(opaque:colorMode:)**: Composites this view’s contents into an offscreen image before final display.
- **BlendMode**: Modes for compositing a view with overlapping content.
- **CompositorContent**
- **CompositorContentBuilder**: A result builder for composing a collection of [CompositorContent](CompositorContent.zh-Hans.md) elements.
- **AnyCompositorContent**: Type erased compositor content.

## Conforms To

- Copyable
- Equatable
- Hashable
- Sendable
- SendableMetatype

