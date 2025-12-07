--- 来源：https://developer.apple.com/documentation/SwiftUI/View/alignmentGuide(_:computeValue:)

抓取时间：2025-12-02T17:38:47Z

---

# alignmentGuide(_:computeValue:)

**实例方法**

设置视图的水平对齐方式。

## 声明

```swift
@preconcurrency nonisolated func alignmentGuide(_ g: HorizontalAlignment, computeValue: @escaping (ViewDimensions) -> CGFloat) -> some View

```

## 参数

- **g**：用于计算偏移量的 [HorizontalAlignment](../HorizontalAlignment.zh-Hans.md) 值。

- **computeValue**：返回要应用于此视图的偏移量的闭包。

## 返回值

根据方法闭包中执行的计算结果，修改视图的水平对齐方式。

## 讨论

使用 `alignmentGuide(_:computeValue:)` 计算特定偏移量，以重新定位视图之间的相对位置。您可以返回一个常量，也可以使用闭包的 [ViewDimensions](../ViewDimensions.zh-Hans.md) 参数来计算返回值。

在下面的示例中，[HStack](../HStack.zh-Hans.md) 向右偏移了 50 个点（以中心为基准）：

```swift
VStack {
    Text("Today's Weather")
        .font(.title)
        .border(.gray)
    HStack {
        Text("🌧")
        Text("Rain & Thunderstorms")
        Text("⛈")
    }
    .alignmentGuide(HorizontalAlignment.center) { _ in  50 }
    .border(.gray)
}
.border(.gray)
```

更改一个视图的对齐方式可能会影响周围的视图。此处，堆栈及其包含的视图之间的偏移量是它们绝对偏移量之差。

## 对齐视图

- **在堆栈内对齐视图**：使用对齐参考线在堆栈内定位视图。

- **跨堆栈对齐视图**：创建自定义对齐方式并使用它来对齐多个堆栈中的视图。

- **Alignment**：在两个轴上进行对齐。

- **HorizontalAlignment**：沿水平轴的对齐位置。

- **VerticalAlignment**：沿垂直轴的对齐位置。

- **DepthAlignment**：沿深度轴的对齐位置。

- **AlignmentID**：用于创建自定义对齐参考线的类型。

- **ViewDimensions**：视图在其自身坐标空间中的大小和对齐参考线。

- **ViewDimensions3D**：视图在其自身坐标空间中 3D 的大小和对齐参考线。

- **SpatialContainer**：用于在 3D 空间中对齐重叠内容的布局容器。


---
source: https://developer.apple.com/documentation/SwiftUI/View/alignmentGuide(_:computeValue:)
crawled: 2025-12-02T17:38:47Z
---

# alignmentGuide(_:computeValue:)

**Instance Method**

Sets the view’s horizontal alignment.

## Declaration

```swift
@preconcurrency nonisolated func alignmentGuide(_ g: HorizontalAlignment, computeValue: @escaping (ViewDimensions) -> CGFloat) -> some View

```

## Parameters

- **g**: A [HorizontalAlignment](../HorizontalAlignment.zh-Hans.md) value at which to base the offset.
- **computeValue**: A closure that returns the offset value to apply to this view.

## Return Value

A view modified with respect to its horizontal alignment according to the computation performed in the method’s closure.

## Discussion

Use `alignmentGuide(_:computeValue:)` to calculate specific offsets to reposition views in relationship to one another. You can return a constant or can use the [ViewDimensions](../ViewDimensions.zh-Hans.md) argument to the closure to calculate a return value.

In the example below, the [HStack](../HStack.zh-Hans.md) is offset by a constant of 50 points to the right of center:

```swift
VStack {
    Text("Today's Weather")
        .font(.title)
        .border(.gray)
    HStack {
        Text("🌧")
        Text("Rain & Thunderstorms")
        Text("⛈")
    }
    .alignmentGuide(HorizontalAlignment.center) { _ in  50 }
    .border(.gray)
}
.border(.gray)
```

Changing the alignment of one view may have effects on surrounding views. Here the offset values inside a stack and its contained views is the difference of their absolute offsets.



## Aligning views

- **Aligning views within a stack**: Position views inside a stack using alignment guides.
- **Aligning views across stacks**: Create a custom alignment and use it to align views across multiple stacks.
- **Alignment**: An alignment in both axes.
- **HorizontalAlignment**: An alignment position along the horizontal axis.
- **VerticalAlignment**: An alignment position along the vertical axis.
- **DepthAlignment**: An alignment position along the depth axis.
- **AlignmentID**: A type that you use to create custom alignment guides.
- **ViewDimensions**: A view’s size and alignment guides in its own coordinate space.
- **ViewDimensions3D**: A view’s 3D size and alignment guides in its own coordinate space.
- **SpatialContainer**: A layout container that aligns overlapping content in 3D space.

