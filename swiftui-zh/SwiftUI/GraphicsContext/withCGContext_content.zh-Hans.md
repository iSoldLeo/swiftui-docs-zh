---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/withCGContext(内容：)
抓取时间： 2025-12-01T00:42:36Z
---

# withCGContext(content:)

**实例方法**

提供一个核心图形上下文，您可以用它作为代理将图形绘制到此上下文中。

## 声明

```swift
func withCGContext(content: (CGContext) throws -> Void) rethrows
```

## 参数

- **content**：接收[doc://com.apple.documentation/documentation/CoreGraphics/CGContext] 的闭包，用于执行绘制操作，就像绘制到[GraphicsContext](../GraphicsContext.zh-Hans.md) 实例中一样。在调用`withCGContext(content:)` 之前设置的任何滤镜、混合模式设置、剪辑蒙版和其他状态也适用于核心图形上下文中的绘图操作。当闭包返回时，在核心图形上下文中设置的任何状态都将丢失。在闭包返回后访问核心图形上下文会产生未定义的行为。

## 讨论

使用此方法可使用依赖 Core Graphics 基元的现有绘图代码。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/withCGContext(content:)
crawled: 2025-12-01T00:42:36Z
---

# withCGContext(content:)

**Instance Method**

Provides a Core Graphics context that you can use as a proxy to draw into this context.

## Declaration

```swift
func withCGContext(content: (CGContext) throws -> Void) rethrows
```

## Parameters

- **content**: A closure that receives a [doc://com.apple.documentation/documentation/CoreGraphics/CGContext] that you use to perform drawing operations, just like you draw into a [GraphicsContext](../GraphicsContext.zh-Hans.md) instance. Any filters, blend mode settings, clip masks, and other state set before calling `withCGContext(content:)` apply to drawing operations in the Core Graphics context as well. Any state you set on the Core Graphics context is lost when the closure returns. Accessing the Core Graphics context after the closure returns produces undefined behavior.

## Discussion

Use this method to use existing drawing code that relies on Core Graphics primitives.

