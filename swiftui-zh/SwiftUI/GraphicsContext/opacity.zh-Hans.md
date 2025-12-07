---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/opacity
抓取时间：2025-12-02T20:58:20Z
---

# 不透明度

**实例属性**

上下文中绘图操作的不透明度。

## 声明

```swift
var opacity: Double { get set }
```

## 讨论

设置此值可影响随后绘制到上下文中的内容的不透明度。更改此值不会影响之前绘制到上下文中的内容。

## 设置不透明度和混合模式

- **blendMode**：在上下文中进行绘制操作时使用的混合模式。
- **GraphicsContext.BlendMode**：图形上下文将新内容与背景内容相结合的方式。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/opacity
crawled: 2025-12-02T20:58:20Z
---

# opacity

**Instance Property**

The opacity of drawing operations in the context.

## Declaration

```swift
var opacity: Double { get set }
```

## Discussion

Set this value to affect the opacity of content that you subsequently draw into the context. Changing this value has no impact on the content you previously drew into the context.

## Setting opacity and the blend mode

- **blendMode**: The blend mode used by drawing operations in the context.
- **GraphicsContext.BlendMode**: The ways that a graphics context combines new content with background content.

