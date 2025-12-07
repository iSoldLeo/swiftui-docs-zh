--- 来源：https://developer.apple.com/documentation/SwiftUI/View/chartXAxisLabel(position:alignment:spacing:content:)

抓取时间：2025-12-01T10:23:12Z

---

# chartXAxisLabel(position:alignment:spacing:content:)

**实例方法**

为视图中的图表添加 x 轴标签。

## 声明

```swift
nonisolated func chartXAxisLabel<C>(position: AnnotationPosition = .automatic, alignment: Alignment? = nil, spacing: CGFloat? = nil, @ViewBuilder content: () -> C) -> some View where C : View

```

## 参数

- **position**：标签的位置。

- **alignment**：标签的对齐方式。

- **spacing**：标签与坐标轴标记之间的间距。

- **content**：标签的内容。

## 坐标轴标签

- **chartXAxisLabel(_:position:alignment:spacing:)**：为视图中的图表添加 x 轴标签。

- **chartYAxisLabel(_:position:alignment:spacing:)**：为视图中的图表添加 y 轴标签。

- **chartYAxisLabel(position:alignment:spacing:content:)**：为视图中的图表添加 y 轴标签。


---
source: https://developer.apple.com/documentation/SwiftUI/View/chartXAxisLabel(position:alignment:spacing:content:)
crawled: 2025-12-01T10:23:12Z
---

# chartXAxisLabel(position:alignment:spacing:content:)

**Instance Method**

Adds x axis label for charts in the view.

## Declaration

```swift
nonisolated func chartXAxisLabel<C>(position: AnnotationPosition = .automatic, alignment: Alignment? = nil, spacing: CGFloat? = nil, @ViewBuilder content: () -> C) -> some View where C : View

```

## Parameters

- **position**: The position of the label.
- **alignment**: The alignment of the label.
- **spacing**: The spacing of the label from the axis markers.
- **content**: The label content.

## Axis Labels

- **chartXAxisLabel(_:position:alignment:spacing:)**: Adds x axis label for charts in the view.
- **chartYAxisLabel(_:position:alignment:spacing:)**: Adds y axis label for charts in the view.
- **chartYAxisLabel(position:alignment:spacing:content:)**: Adds y axis label for charts in the view.

