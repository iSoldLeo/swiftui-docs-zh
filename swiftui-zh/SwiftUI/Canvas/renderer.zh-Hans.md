---
来源： https://developer.apple.com/documentation/SwiftUI/Canvas/renderer
抓取时间： 2025-12-02T20:58:03Z
---

# 渲染器

**实例属性**

用于绘制画布的绘制回调。

## 声明

```swift
var renderer: (inout GraphicsContext, CGSize) -> Void
```

## 参数

- **context**：要绘制的图形上下文。
- **size**：视图的当前大小。

## 渲染

- **rendersAsynchronously**：布尔值，表示画布是否可以异步向父视图显示其内容。


---
source: https://developer.apple.com/documentation/SwiftUI/Canvas/renderer
crawled: 2025-12-02T20:58:03Z
---

# renderer

**Instance Property**

The drawing callback that you use to draw into the canvas.

## Declaration

```swift
var renderer: (inout GraphicsContext, CGSize) -> Void
```

## Parameters

- **context**: The graphics context to draw into.
- **size**: The current size of the view.

## Rendering

- **rendersAsynchronously**: A Boolean that indicates whether the canvas can present its contents to its parent view asynchronously.

