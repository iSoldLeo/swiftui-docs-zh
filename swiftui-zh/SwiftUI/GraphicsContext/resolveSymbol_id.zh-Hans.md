---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/resolveSymbol(id:)
抓取时间：2025-12-02T20:58:12Z
---

# resolveSymbol(id:)

**实例方法**

如果存在已识别的子视图，则以已解析符号的形式获取该视图。

## 声明

```swift
func resolveSymbol<ID>(id: ID) -> GraphicsContext.ResolvedSymbol? where ID : Hashable
```

## 参数

- **id**：在`symbols` 初始化器的[Canvas](../Canvas.zh-Hans.md) 参数中定义视图时用于标记视图的值 [init(opaque:colorMode:rendersAsynchronously:renderer:symbols:)](../Canvas/init_opaque_colorMode_rendersAsynchronously_renderer_symbols.zh-Hans.md)。

## 返回值

已解析的符号，如果 SwiftUI 无法找到与给定`id` 一致的子视图，则返回 `nil`。

## 解决绘制的实体

- **resolve(_:)**：获取与图形上下文环境的当前值固定的图像版本。
- **GraphicsContext.ResolvedSymbol**：可多次绘制的静态绘图操作序列，保持其分辨率的独立性。
- **GraphicsContext.ResolvedImage**：根据特定环境解析的图像。
- **GraphicsContext.ResolvedText**：解析到特定环境的文本视图。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/resolveSymbol(id:)
crawled: 2025-12-02T20:58:12Z
---

# resolveSymbol(id:)

**Instance Method**

Gets the identified child view as a resolved symbol, if the view exists.

## Declaration

```swift
func resolveSymbol<ID>(id: ID) -> GraphicsContext.ResolvedSymbol? where ID : Hashable
```

## Parameters

- **id**: The value that you used to tag the view when you define it in the `symbols` parameter of the [Canvas](../Canvas.zh-Hans.md) initializer [init(opaque:colorMode:rendersAsynchronously:renderer:symbols:)](../Canvas/init_opaque_colorMode_rendersAsynchronously_renderer_symbols.zh-Hans.md).

## Return Value

The resolved symbol, or `nil` if SwiftUI can’t find a child view with the given `id`.

## Resolving a drawn entity

- **resolve(_:)**: Gets a version of an image that’s fixed with the current values of the graphics context’s environment.
- **GraphicsContext.ResolvedSymbol**: A static sequence of drawing operations that may be drawn multiple times, preserving their resolution independence.
- **GraphicsContext.ResolvedImage**: An image resolved to a particular environment.
- **GraphicsContext.ResolvedText**: A text view resolved to a particular environment.

