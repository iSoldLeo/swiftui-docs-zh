--- 来源：https://developer.apple.com/documentation/SwiftUI/VStack/init(alignment:spacing:content:)

抓取时间：2025-12-01T02:45:53Z

---

# init(alignment:spacing:content:)

**Initializer**

创建一个具有指定间距和水平对齐方式的实例。

## 声明

```swift
init(alignment: HorizontalAlignment = .center, spacing: CGFloat? = nil, @ViewBuilder content: () -> Content)
```

## 参数

- **alignment**：此堆栈中子视图的对齐参考线。此参考线对每个子视图具有相同的垂直屏幕坐标。

- **spacing**：相邻子视图之间的距离，或者如果您希望堆栈为每对子视图选择默认距离，则使用 `nil`。

- **content**：用于创建此堆栈内容的视图构建器。


---
source: https://developer.apple.com/documentation/SwiftUI/VStack/init(alignment:spacing:content:)
crawled: 2025-12-01T02:45:53Z
---

# init(alignment:spacing:content:)

**Initializer**

Creates an instance with the given spacing and horizontal alignment.

## Declaration

```swift
init(alignment: HorizontalAlignment = .center, spacing: CGFloat? = nil, @ViewBuilder content: () -> Content)
```

## Parameters

- **alignment**: The guide for aligning the subviews in this stack. This guide has the same vertical screen coordinate for every subview.
- **spacing**: The distance between adjacent subviews, or `nil` if you want the stack to choose a default distance for each pair of subviews.
- **content**: A view builder that creates the content of this stack.

