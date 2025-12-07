--- 来源：https://developer.apple.com/documentation/SwiftUI/View/chartXAxisLabel(_:position:alignment:spacing:)

抓取时间：2025-12-03T05:34:07Z

---

# chartXAxisLabel(_:position:alignment:spacing:)

**实例方法**

为视图中的图表添加 x 轴标签。

## 声明

```swift
nonisolated func chartXAxisLabel(_ labelKey: LocalizedStringKey, position: AnnotationPosition = .automatic, alignment: Alignment? = nil, spacing: CGFloat? = nil) -> some View

```

## 参数

- **labelKey**：本地化标签字符串的键。

- **position**：标签的位置。

- **alignment**：标签的对齐方式。

- **spacing**：标签与坐标轴标记之间的间距。

## 坐标轴标签

- **chartXAxisLabel(position:alignment:spacing:content:)**：为视图中的图表添加 x 轴标签。

- **chartYAxisLabel(_:position:alignment:spacing:)**：为视图中的图表添加 y 轴标签。

- **chartYAxisLabel(position:alignment:spacing:content:)**：为视图中的图表添加 y 轴标签。


---
source: https://developer.apple.com/documentation/SwiftUI/View/chartXAxisLabel(_:position:alignment:spacing:)
crawled: 2025-12-03T05:34:07Z
---

# chartXAxisLabel(_:position:alignment:spacing:)

**Instance Method**

Adds x axis label for charts in the view.

## Declaration

```swift
nonisolated func chartXAxisLabel(_ labelKey: LocalizedStringKey, position: AnnotationPosition = .automatic, alignment: Alignment? = nil, spacing: CGFloat? = nil) -> some View

```

## Parameters

- **labelKey**: The key for the localized label string.
- **position**: The position of the label.
- **alignment**: The alignment of the label.
- **spacing**: The spacing of the label from the axis markers.

## Axis Labels

- **chartXAxisLabel(position:alignment:spacing:content:)**: Adds x axis label for charts in the view.
- **chartYAxisLabel(_:position:alignment:spacing:)**: Adds y axis label for charts in the view.
- **chartYAxisLabel(position:alignment:spacing:content:)**: Adds y axis label for charts in the view.

