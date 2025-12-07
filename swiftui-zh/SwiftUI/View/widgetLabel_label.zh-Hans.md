--- 来源：https://developer.apple.com/documentation/SwiftUI/View/widgetLabel(label:)

抓取时间：2025-11-30T21:17:11Z

---

# widgetLabel(label:)

**实例方法**

创建一个标签，用于在辅助组件主 SwiftUI 视图之外显示附加内容。

## 声明

```swift
@MainActor @preconcurrency func widgetLabel<Label>(@ViewBuilder label: () -> Label) -> some View where Label : View

```

## 参数

- **label**：WidgetKit 可以与辅助组件主 SwiftUI 视图一起显示的视图。您可以使用 [doc://com.apple.documentation/documentation/SwiftUI/Image]、[doc://com.apple.documentation/documentation/SwiftUI/Text]、[doc://com.apple.documentation/documentation/SwiftUI/Gauge]、[doc://com.apple.documentation/documentation/SwiftUI/ProgressView]，或者包含多个子视图的容器。

## 讨论

系统仅在 watchOS 中基于小组件的复杂功能上显示标签。系统会忽略 iPhone 锁屏界面上附加到小组件的任何标签。因此，您可以使用相同的代码在 iPhone 和 Apple Watch 上显示配件系列小组件。

要创建小组件标签，请在复杂功能的主 SwiftUI 视图上调用 `IC_0004`。将所需内容作为 `IC_0003` 参数传递。标签可以是 `DL_0009`、`DL_0008`、`DL_0007` 或 `DL_0006`。要提供多个视图，请将视图包装在容器中，例如 `DL_0005`。WidgetKit 会判断是否可以使用标签的任何内容。如果不能，则会忽略该标签。

```swift

  struct Complication: View {
      @Environment(\.widgetFamily) var widgetFamily

      var body: some View {
          switch widgetFamily {
          case .accessoryCorner:
              Text("Hi")
                  .widgetLabel {
                      Gauge(value: 0.8)
                  }
          case .accessoryCircular:
              VStack {
                  Image(systemName: "emoji.globe")
                  Text("Hi")
              }
              .widgetLabel("World!")
          case .accessoryInline:
              Text("\(Image(systemName: "emoji.globe.face")) World!")
      }
  }

```

WidgetKit 会配置标签，使表盘呈现统一的外观。例如，它可以设置图像的大小、文本的字体，甚至可以沿着曲线渲染文本和仪表盘。

以下组件系列支持组件标签：

但是，WidgetKit 仅在信息图表表盘（顶部圆形复杂功能）的表圈上渲染标签。在所有其他圆形复杂功能（包括所有其他平台上的组件）上，WidgetKit 会忽略标签。

## 为组件添加标签

- **widgetLabel(_:)**：返回一个本地化的文本标签，用于在配件系列组件的主 SwiftUI 视图之外显示附加内容。


---
source: https://developer.apple.com/documentation/SwiftUI/View/widgetLabel(label:)
crawled: 2025-11-30T21:17:11Z
---

# widgetLabel(label:)

**Instance Method**

Creates a label for displaying additional content outside an accessory family widget’s main SwiftUI view.

## Declaration

```swift
@MainActor @preconcurrency func widgetLabel<Label>(@ViewBuilder label: () -> Label) -> some View where Label : View

```

## Parameters

- **label**: A view that WidgetKit can display alongside the accessory family widget’s main SwiftUI view. You can use a [doc://com.apple.documentation/documentation/SwiftUI/Image], [doc://com.apple.documentation/documentation/SwiftUI/Text], [doc://com.apple.documentation/documentation/SwiftUI/Gauge], [doc://com.apple.documentation/documentation/SwiftUI/ProgressView], or a container with multiple subviews.

## Discussion

The system only displays labels on widget-based complications in watchOS. The system ignores any labels attached to widgets on the Lock Screen on iPhone. Therefore, you can use the same code to display an accessory family widget on both iPhone and Apple Watch.

To create the widget label, call `widgetLabel(label:)`on a complication’s main SwiftUI view. Pass the desired content as the `label` parameter. The label can be a [doc://com.apple.documentation/documentation/SwiftUI/Gauge], [doc://com.apple.documentation/documentation/SwiftUI/ProgressView], [doc://com.apple.documentation/documentation/SwiftUI/Text], or [doc://com.apple.documentation/documentation/SwiftUI/Image]. To provide multiple views, wrap your views in a container, such as a [doc://com.apple.documentation/documentation/SwiftUI/VStack]. WidgetKit determines whether it can use any of the label’s content. If it can’t, it ignores the label.

```swift

  struct Complication: View {
      @Environment(\.widgetFamily) var widgetFamily

      var body: some View {
          switch widgetFamily {
          case .accessoryCorner:
              Text("Hi")
                  .widgetLabel {
                      Gauge(value: 0.8)
                  }
          case .accessoryCircular:
              VStack {
                  Image(systemName: "emoji.globe")
                  Text("Hi")
              }
              .widgetLabel("World!")
          case .accessoryInline:
              Text("\(Image(systemName: "emoji.globe.face")) World!")
      }
  }

```

WidgetKit configures the label so that the watch face presents a unified look. For example, it sets the size for an image, the font for text, and can even render text and gauges along a curve.

The following widget families support widget labels:



However, WidgetKit only renders the label along the bezel on the Infograph watch face (the top circular complication). On all other circular complications — including widgets on all other platforms — WidgetKit ignores the label.

## Labeling a widget

- **widgetLabel(_:)**: Returns a localized text label that displays additional content outside the accessory family widget’s main SwiftUI view.

