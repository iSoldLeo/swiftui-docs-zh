---
来源： https://developer.apple.com/documentation/SwiftUI/TextRenderer
抓取时间： 2025-12-02T16:16:08Z
---

# 文本渲染器

**Protocol**

可替换默认文本视图渲染行为的值。

## 声明

```swift
protocol TextRenderer : Animatable
```

## 实例属性

- **displayPadding**：返回用于光栅化文本的任何绘图层中添加的额外填充的大小。例如，在绘制带有阴影的文本时，可以使用此值来扩展绘制边界，以避免剪切阴影。

### 实例方法

- **draw(layout:in:)**：将 `layout` 绘制到 `ctx` 中。
- **sizeThatFits(proposal:text:)**：返回`proposal`中文本的大小。提供的`text` 代理值可用于查询底层文本布局的大小行为。

## 渲染文本

- 使用 SwiftUI 创建视觉效果**：使用着色器和文本渲染器添加滚动效果、丰富的色彩处理、自定义过渡效果和高级效果。
- **TextAttribute**：可附加到文本视图的值，文本呈现器可对其进行查询。
- **textRenderer(_:)**：返回一个新视图，其中的任何文本视图都将使用`renderer` 进行绘制。
- **TextProxy**：自定义文本呈现器使用的文本视图代理。

## 继承自

- 动画


---
source: https://developer.apple.com/documentation/SwiftUI/TextRenderer
crawled: 2025-12-02T16:16:08Z
---

# TextRenderer

**Protocol**

A value that can replace the default text view rendering behavior.

## Declaration

```swift
protocol TextRenderer : Animatable
```

## Instance Properties

- **displayPadding**: Returns the size of the extra padding added to any drawing layer used to rasterize the text. For example when drawing the text with a shadow this may be used to extend the drawing bounds to avoid clipping the shadow.

## Instance Methods

- **draw(layout:in:)**: Draws `layout` into `ctx`.
- **sizeThatFits(proposal:text:)**: Returns the size of the text in `proposal`. The provided `text` proxy value may be used to query the sizing behavior of the underlying text layout.

## Rendering text

- **Creating visual effects with SwiftUI**: Add scroll effects, rich color treatments, custom transitions, and advanced effects using shaders and a text renderer.
- **TextAttribute**: A value that you can attach to text views and that text renderers can query.
- **textRenderer(_:)**: Returns a new view such that any text views within it will use `renderer` to draw themselves.
- **TextProxy**: A proxy for a text view that custom text renderers use.

## Inherits From

- Animatable

