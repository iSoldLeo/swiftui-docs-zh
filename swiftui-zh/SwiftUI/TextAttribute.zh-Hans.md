---
来源： https://developer.apple.com/documentation/SwiftUI/TextAttribute
抓取时间： 2025-12-02T16:16:07Z
---

# 文本属性

**Protocol**

可以附加到文本视图的值，文本呈现器可以查询该值。

## 声明

```swift
protocol TextAttribute : Hashable
```

## 渲染文本

- 使用 SwiftUI 创建视觉效果**：使用着色器和文本渲染器添加滚动效果、丰富的色彩处理、自定义过渡效果和高级效果。
- **textRenderer(_:)**：返回一个新视图，其中的任何文本视图都将使用`renderer` 进行绘制。
- **TextRenderer**：可替换默认文本视图渲染行为的值。
- **TextProxy**：自定义文本呈现器使用的文本视图的代理。

## 继承自

- 等价
- 散列


---
source: https://developer.apple.com/documentation/SwiftUI/TextAttribute
crawled: 2025-12-02T16:16:07Z
---

# TextAttribute

**Protocol**

A value that you can attach to text views and that text renderers can query.

## Declaration

```swift
protocol TextAttribute : Hashable
```

## Rendering text

- **Creating visual effects with SwiftUI**: Add scroll effects, rich color treatments, custom transitions, and advanced effects using shaders and a text renderer.
- **textRenderer(_:)**: Returns a new view such that any text views within it will use `renderer` to draw themselves.
- **TextRenderer**: A value that can replace the default text view rendering behavior.
- **TextProxy**: A proxy for a text view that custom text renderers use.

## Inherits From

- Equatable
- Hashable

