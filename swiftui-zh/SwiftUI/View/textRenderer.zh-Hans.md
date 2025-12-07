--- 来源：https://developer.apple.com/documentation/SwiftUI/View/textRenderer(_:)

抓取时间：2025-11-30T20:01:21Z

---

# textRenderer(_:)

**实例方法**

返回一个新的视图，其中所有文本视图都将使用 `renderer` 进行绘制。

## 声明

```swift
nonisolated func textRenderer<T>(_ renderer: T) -> some View where T : TextRenderer

```

## 参数

- **renderer**：渲染器值。

## 返回值

一个新的视图，它将使用 `renderer` 绘制其文本视图。

## 渲染文本

- **使用 SwiftUI 创建视觉效果**：使用着色器和文本渲染器添加滚动效果、丰富的色彩处理、自定义过渡效果和高级效果。

- **TextAttribute**：可附加到文本视图的值，文本渲染器可以查询该值。

- **TextRenderer**：可替换默认文本视图渲染行为的值。

- **TextProxy**：自定义文本渲染器使用的文本视图代理。


---
source: https://developer.apple.com/documentation/SwiftUI/View/textRenderer(_:)
crawled: 2025-11-30T20:01:21Z
---

# textRenderer(_:)

**Instance Method**

Returns a new view such that any text views within it will use `renderer` to draw themselves.

## Declaration

```swift
nonisolated func textRenderer<T>(_ renderer: T) -> some View where T : TextRenderer

```

## Parameters

- **renderer**: The renderer value.

## Return Value

A new view that will use `renderer` to draw its text views.

## Rendering text

- **Creating visual effects with SwiftUI**: Add scroll effects, rich color treatments, custom transitions, and advanced effects using shaders and a text renderer.
- **TextAttribute**: A value that you can attach to text views and that text renderers can query.
- **TextRenderer**: A value that can replace the default text view rendering behavior.
- **TextProxy**: A proxy for a text view that custom text renderers use.

