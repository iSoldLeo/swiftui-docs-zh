--- 来源：https://developer.apple.com/documentation/SwiftUI/View/widgetLabel(_:)

抓取时间：2025-12-02T17:32:05Z

---

# widgetLabel(_:)

**实例方法**

返回一个本地化的文本标签，用于在配件系列组件的主 SwiftUI 视图之外显示附加内容。

## 声明

```swift
@MainActor @preconcurrency func widgetLabel(_ label: LocalizedStringResource) -> some View

```

## 参数

- **label**：由本地化字符串生成的标签。

## 说明

要向配件系列组件添加文本标签，请在组件的主 SwiftUI 视图上调用此方法，并传入一个受支持的 `LocalizedStringResource`。系统会判断是否可以使用该文本标签。如果不能，则会忽略该标签。系统还会根据表盘设置标签的大小、位置和样式。例如，设置字体并沿曲线渲染文本。

以下组件系列支持文本配件标签：

- 基于组件的复杂功能 [doc://com.apple.documentation/documentation/WidgetKit/WidgetFamily/accessoryCorner] 可以在表盘角落的内侧边缘显示弧形文本标签。向配件角落复杂功能添加标签会导致主 SwiftUI 视图缩小，以便为标签腾出空间。

- 组件 [doc://com.apple.documentation/documentation/WidgetKit/WidgetFamily/accessoryCircular] 可以在 watchOS 中显示文本标签；但是，WidgetKit 仅在信息图表表盘（顶部圆形复杂功能）的表圈上渲染标签。

## 为组件添加标签

- **widgetLabel(label:)**：创建一个标签，用于在配件系列组件的主 SwiftUI 视图之外显示附加内容。


---
source: https://developer.apple.com/documentation/SwiftUI/View/widgetLabel(_:)
crawled: 2025-12-02T17:32:05Z
---

# widgetLabel(_:)

**Instance Method**

Returns a localized text label that displays additional content outside the accessory family widget’s main SwiftUI view.

## Declaration

```swift
@MainActor @preconcurrency func widgetLabel(_ label: LocalizedStringResource) -> some View

```

## Parameters

- **label**: A label generated from a localized string.

## Discussion

To add a text label to an accessory family widget, call this method on the widget’s main SwiftUI view, and pass in a supported `LocalizedStringResource`. The system determines whether it can use the text label. If it can’t, it ignores the label. The system also sets the label’s size, placement, and style based on the clock face. For example, setting the font and rendering the text along a curve.

The following widget families support text accessory labels:

- The [doc://com.apple.documentation/documentation/WidgetKit/WidgetFamily/accessoryCorner] widget-based complication can display a curved text label on the inside edge of the corner. Adding a label to an accessory corner complication causes the main SwiftUI view to shrink to make space for the label.
- The [doc://com.apple.documentation/documentation/WidgetKit/WidgetFamily/accessoryCircular] widget can display a text label in watchOS; however, WidgetKit only renders the label along the bezel on the Infograph watch face (the top circular complication).

## Labeling a widget

- **widgetLabel(label:)**: Creates a label for displaying additional content outside an accessory family widget’s main SwiftUI view.

