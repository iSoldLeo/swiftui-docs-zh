---
来源：https://developer.apple.com/documentation/SwiftUI/GraphicsContext/draw(_:in:)
抓取时间： 2025-12-01T00:42:16Z
---

# draw(_:in:)

**实例方法**

使用指定的矩形作为布局框架，在上下文中绘制已解析的符号。

## 声明

```swift
func draw(_ symbol: GraphicsContext.ResolvedSymbol, in rect: CGRect)
```

## 参数

- **symbol**：要绘制的[ResolvedSymbol](ResolvedSymbol.zh-Hans.md)。使用在[Canvas](../Canvas.zh-Hans.md) 初始化过程中用来标记相应子视图的标识符调用[resolveSymbol(id:)](resolveSymbol_id.zh-Hans.md)，获取已解析的符号。
- **rect**：在当前用户空间中绘制符号的矩形。

## 讨论

当前上下文状态定义了整个绘制操作。例如，当前变换和剪切形状会影响 SwiftUI 绘制符号的方式。

## 绘制图像、文本和视图

- **draw(_:in:style:)**：使用指定的矩形作为布局框架，在上下文中绘制已解析的图像。
- **draw(_:at:anchor:)**：在上下文中绘制解析图像，将图像中的锚点与上下文中的点对齐。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/draw(_:in:)
crawled: 2025-12-01T00:42:16Z
---

# draw(_:in:)

**Instance Method**

Draws a resolved symbol into the context, using the specified rectangle as a layout frame.

## Declaration

```swift
func draw(_ symbol: GraphicsContext.ResolvedSymbol, in rect: CGRect)
```

## Parameters

- **symbol**: The [ResolvedSymbol](ResolvedSymbol.zh-Hans.md) to draw. Get a resolved symbol by calling [resolveSymbol(id:)](resolveSymbol_id.zh-Hans.md) with the identifier that you use to tag the corresponding child view during [Canvas](../Canvas.zh-Hans.md) initialization.
- **rect**: The rectangle in the current user space to draw the symbol in.

## Discussion

The current context state defines the full drawing operation. For example, the current transformation and clip shapes affect how SwiftUI draws the symbol.

## Drawing images, text, and views

- **draw(_:in:style:)**: Draws a resolved image into the context, using the specified rectangle as a layout frame.
- **draw(_:at:anchor:)**: Draws a resolved image into the context, aligning an anchor within the image to a point in the context.

