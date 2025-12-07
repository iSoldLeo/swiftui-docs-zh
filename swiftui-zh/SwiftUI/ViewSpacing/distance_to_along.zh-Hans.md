---
来源：https://developer.apple.com/documentation/SwiftUI/ViewSpacing/distance(到:沿:)
抓取时间： 2025-12-03T06:39:33Z
---

# distance(to:along:)

**实例方法**

沿指定轴向获取返回指定间距首选项的视图的首选间距。

## 声明

```swift
func distance(to next: ViewSpacing, along axis: Axis) -> CGFloat
```

## 参数

- **next**：相邻视图的间距首选项实例。
- **axis**：两个视图对齐的轴线。

## 返回值

一个浮点数值，表示两个视图之间满足本视图和共享边缘上相邻视图间距偏好的最小点间距。

## 讨论

如果需要测量自定义布局中两个视图之间的默认间距，请在[Layout](../Layout.zh-Hans.md) 协议方法的实现中调用此方法。在第一个视图的首选项实例上调用该方法，并提供第二个视图的首选项实例作为输入。

例如，考虑在自定义水平堆叠中出现的两个视图。下面的距离调用会获取这两个视图之间的首选间距，其中`spacing1` 包含第一个视图的首选项，`spacing2` 包含第二个视图的首选项：

```swift
let distance = spacing1.distance(to: spacing2, axis: .horizontal)
```

该方法首先根据轴线和排序确定两个视图在第一个视图的后缘和第二个视图的前缘相邻。然后获取每个视图对应边缘的间距偏好，并返回两个值中较大的值。这样得到的最小值就能提供足够的空间来满足两个视图的偏好。




---
source: https://developer.apple.com/documentation/SwiftUI/ViewSpacing/distance(to:along:)
crawled: 2025-12-03T06:39:33Z
---

# distance(to:along:)

**Instance Method**

Gets the preferred spacing distance along the specified axis to the view that returns a specified spacing preference.

## Declaration

```swift
func distance(to next: ViewSpacing, along axis: Axis) -> CGFloat
```

## Parameters

- **next**: The spacing preferences instance of the adjacent view.
- **axis**: The axis that the two views align on.

## Return Value

A floating point value that represents the smallest distance in points between two views that satisfies the spacing preferences of both this view and the adjacent views on their shared edge.

## Discussion

Call this method from your implementation of [Layout](../Layout.zh-Hans.md) protocol methods if you need to measure the default spacing between two views in a custom layout. Call the method on the first view’s preferences instance, and provide the second view’s preferences instance as input.

For example, consider two views that appear in a custom horizontal stack. The following distance call gets the preferred spacing between these views, where `spacing1` contains the preferences of a first view, and `spacing2` contains the preferences of a second view:

```swift
let distance = spacing1.distance(to: spacing2, axis: .horizontal)
```

The method first determines, based on the axis and the ordering, that the views abut on the trailing edge of the first view and the leading edge of the second. It then gets the spacing preferences for the corresponding edges of each view, and returns the greater of the two values. This results in the smallest value that provides enough space to satisfy the preferences of both views.



