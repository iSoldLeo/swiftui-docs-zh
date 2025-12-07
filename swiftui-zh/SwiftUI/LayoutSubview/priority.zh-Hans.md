---
来源： https://developer.apple.com/documentation/SwiftUI/LayoutSubview/priority
抓取时间： 2025-12-02T20:59:11Z
---

# 优先级

**实例属性**

子视图的布局优先级。

## 声明

```swift
var priority: Double { get }
```

## 讨论

如果使用[Layout](../Layout.zh-Hans.md) 协议定义了自定义布局类型，就可以从子视图中读取该值，并在决定如何为子视图分配空间时使用该值。例如，在将子视图放入名为`BasicVStack` 的自定义布局类型之前，可以将所有子视图的优先级读入一个数组：

```swift
extension BasicVStack {
    func placeSubviews(
        in bounds: CGRect,
        proposal: ProposedViewSize,
        subviews: Subviews,
        cache: inout ()
    ) {
        let priorities = subviews.map { subview in
            subview.priority
        }

        // Place views, based on priorities.
    }
}
```

通过应用[layoutPriority(_:)](../View/layoutPriority.zh-Hans.md) 视图修饰符，为布局中出现的视图设置布局优先级。例如，您可以为使用 `BasicVStack` 安排的视图指定两种不同的优先级：

```swift
BasicVStack {
    Text("High priority")
        .layoutPriority(10)
    Text("Low priority")
        .layoutPriority(1)
}
```

## 获取子视图特征

- **dimensions(in:)**：询问子视图的尺寸和对齐方式。
- **sizeThatFits(_:)**：询问子视图的尺寸。
- **spacing**：询问子视图的尺寸：子视图的首选间距值。


---
source: https://developer.apple.com/documentation/SwiftUI/LayoutSubview/priority
crawled: 2025-12-02T20:59:11Z
---

# priority

**Instance Property**

The layout priority of the subview.

## Declaration

```swift
var priority: Double { get }
```

## Discussion

If you define a custom layout type using the [Layout](../Layout.zh-Hans.md) protocol, you can read this value from subviews and use the value when deciding how to assign space to subviews. For example, you can read all of the subview priorities into an array before placing the subviews in a custom layout type called `BasicVStack`:

```swift
extension BasicVStack {
    func placeSubviews(
        in bounds: CGRect,
        proposal: ProposedViewSize,
        subviews: Subviews,
        cache: inout ()
    ) {
        let priorities = subviews.map { subview in
            subview.priority
        }

        // Place views, based on priorities.
    }
}
```

Set the layout priority for a view that appears in your layout by applying the [layoutPriority(_:)](../View/layoutPriority.zh-Hans.md) view modifier. For example, you can assign two different priorities to views that you arrange with `BasicVStack`:

```swift
BasicVStack {
    Text("High priority")
        .layoutPriority(10)
    Text("Low priority")
        .layoutPriority(1)
}
```

## Getting subview characteristics

- **dimensions(in:)**: Asks the subview for its dimensions and alignment guides.
- **sizeThatFits(_:)**: Asks the subview for its size.
- **spacing**: The subviews’s preferred spacing values.

