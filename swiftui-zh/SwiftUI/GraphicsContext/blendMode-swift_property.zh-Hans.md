---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/blendMode-swift.property
抓取时间： 2025-12-02T20:58:21Z
---

# 混合模式

**实例属性**

上下文中绘图操作使用的混合模式。

## 声明

```swift
var blendMode: GraphicsContext.BlendMode { get set }
```

## 讨论

设置此值可影响随后绘制到上下文中的任何内容与上下文中已有内容的混合效果。请使用其中一个[BlendMode-swift.struct](BlendMode-swift_struct.zh-Hans.md) 值。

## 设置不透明度和混合模式

- **opacity**：上下文中绘图操作的不透明度。
- **GraphicsContext.BlendMode**：图形上下文将新内容与背景内容相结合的方式。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/blendMode-swift.property
crawled: 2025-12-02T20:58:21Z
---

# blendMode

**Instance Property**

The blend mode used by drawing operations in the context.

## Declaration

```swift
var blendMode: GraphicsContext.BlendMode { get set }
```

## Discussion

Set this value to affect how any content that you subsequently draw into the context blends with content that’s already in the context. Use one of the [BlendMode-swift.struct](BlendMode-swift_struct.zh-Hans.md) values.

## Setting opacity and the blend mode

- **opacity**: The opacity of drawing operations in the context.
- **GraphicsContext.BlendMode**: The ways that a graphics context combines new content with background content.

