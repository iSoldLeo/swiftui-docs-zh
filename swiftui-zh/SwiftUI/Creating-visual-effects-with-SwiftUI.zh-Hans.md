--- 来源：https://developer.apple.com/documentation/SwiftUI/Creating-visual-effects-with-SwiftUI
抓取时间：2025-12-02T15:51:01Z

---

# 使用 SwiftUI 创建视觉效果

**示例代码**

使用着色器和文本渲染器添加滚动效果、丰富的色彩处理、自定义过渡效果和高级效果。

## 概述

## 渲染文本

- **TextAttribute**：可附加到文本视图的值，文本渲染器可以查询该值。

- **textRenderer(_:)**：返回一个新视图，其中的任何文本视图都将使用 `renderer` 来绘制自身。

- **TextRenderer**：可替换默认文本视图渲染行为的值。

- **TextProxy**：自定义文本渲染器使用的文本视图代理。


---
source: https://developer.apple.com/documentation/SwiftUI/Creating-visual-effects-with-SwiftUI
crawled: 2025-12-02T15:51:01Z
---

# Creating visual effects with SwiftUI

**Sample Code**

Add scroll effects, rich color treatments, custom transitions, and advanced effects using shaders and a text renderer.

## Overview



## Rendering text

- **TextAttribute**: A value that you can attach to text views and that text renderers can query.
- **textRenderer(_:)**: Returns a new view such that any text views within it will use `renderer` to draw themselves.
- **TextRenderer**: A value that can replace the default text view rendering behavior.
- **TextProxy**: A proxy for a text view that custom text renderers use.

