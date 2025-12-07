--- 来源：https://developer.apple.com/documentation/SwiftUI/HStackLayout/init(alignment:spacing:)

抓取时间：2025-12-03T06:39:37Z

---

# init(alignment:spacing:)

**Initializer**

创建一个具有指定间距和垂直对齐方式的水平堆叠。

## 声明

```swift
init(alignment: VerticalAlignment = .center, spacing: CGFloat? = nil)
```

## 参数

- **alignment**：用于对齐此堆叠中子视图的参考线。所有子视图具有相同的垂直屏幕坐标。

- **spacing**：相邻子视图之间的距离。将此值设置为 `nil` 可使用子视图之间的默认距离。


---
source: https://developer.apple.com/documentation/SwiftUI/HStackLayout/init(alignment:spacing:)
crawled: 2025-12-03T06:39:37Z
---

# init(alignment:spacing:)

**Initializer**

Creates a horizontal stack with the specified spacing and vertical alignment.

## Declaration

```swift
init(alignment: VerticalAlignment = .center, spacing: CGFloat? = nil)
```

## Parameters

- **alignment**: The guide for aligning the subviews in this stack. It has the same vertical screen coordinate for all subviews.
- **spacing**: The distance between adjacent subviews. Set this value to `nil` to use default distances between subviews.

