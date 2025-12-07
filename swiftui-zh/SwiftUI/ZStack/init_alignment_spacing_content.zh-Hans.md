--- 来源：https://developer.apple.com/documentation/SwiftUI/ZStack/init(alignment:spacing:content:)

抓取时间：2025-12-01T02:45:26Z

---

# init(alignment:spacing:content:)

**Initializer**

创建一个具有指定间距和对齐方式的实例。

## 声明

```swift
init<V>(alignment: Alignment = .center, spacing: CGFloat?, @ViewBuilder content: () -> V) where Content == ZStackContent3D<V>, V : View
```

## 参数

- **alignment**：用于在 x 轴和 y 轴上对齐此堆栈中子视图的参考线。

- **spacing**：相邻子视图之间的距离，或者使用 `nil`，如果您希望堆栈为每对子视图选择默认距离。

- **content**：用于创建此堆栈内容的视图构建器。


---
source: https://developer.apple.com/documentation/SwiftUI/ZStack/init(alignment:spacing:content:)
crawled: 2025-12-01T02:45:26Z
---

# init(alignment:spacing:content:)

**Initializer**

Creates an instance with the given spacing and alignment.

## Declaration

```swift
init<V>(alignment: Alignment = .center, spacing: CGFloat?, @ViewBuilder content: () -> V) where Content == ZStackContent3D<V>, V : View
```

## Parameters

- **alignment**: The guide for aligning the subviews in this stack on both the x- and y-axes.
- **spacing**: The distance between adjacent subviews, or `nil` if you want the stack to choose a default distance for each pair of subviews.
- **content**: A view builder that creates the content of this stack.

