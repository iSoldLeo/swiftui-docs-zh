---
来源：https://developer.apple.com/documentation/SwiftUI/HStack/init(对齐方式:间距:内容:)
抓取时间： 2025-12-01T10:31:25Z
---

# init(alignment:spacing:content:)

**Initializer**

以给定的间距和垂直对齐方式创建水平堆栈。

## 声明

```swift
init(alignment: VerticalAlignment = .center, spacing: CGFloat? = nil, @ViewBuilder content: () -> Content)
```

## 参数

- **alignment**：用于对齐此堆栈中子视图的向导。每个子视图的垂直屏幕坐标都相同。
- **spacing**：相邻子视图之间的距离，如果希望堆栈为每对子视图选择默认距离，则输入 `nil`。
- **content**：创建此堆栈内容的视图创建器。


---
source: https://developer.apple.com/documentation/SwiftUI/HStack/init(alignment:spacing:content:)
crawled: 2025-12-01T10:31:25Z
---

# init(alignment:spacing:content:)

**Initializer**

Creates a horizontal stack with the given spacing and vertical alignment.

## Declaration

```swift
init(alignment: VerticalAlignment = .center, spacing: CGFloat? = nil, @ViewBuilder content: () -> Content)
```

## Parameters

- **alignment**: The guide for aligning the subviews in this stack. This guide has the same vertical screen coordinate for every subview.
- **spacing**: The distance between adjacent subviews, or `nil` if you want the stack to choose a default distance for each pair of subviews.
- **content**: A view builder that creates the content of this stack.

