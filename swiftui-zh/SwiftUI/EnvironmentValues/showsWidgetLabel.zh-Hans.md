---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/showsWidgetLabel
抓取时间： 2025-12-03T06:07:29Z
---

# showsWidgetLabel

**实例属性**

一个布尔值，用于指示配件系列 widget 是否可以显示配件标签。

### 声明

```swift
var showsWidgetLabel: Bool { get set }
```

## 讨论

使用此值可确定是否可以提供额外内容，或将部件的部分内容移出主视图，放到部件标签中。

```swift

@Environment(\.widgetFamily) var widgetFamily
@Environment(\.showsWidgetLabel) var showsWidgetLabel

var body: some View {
   switch widgetFamily {
   case .accessoryCircular:
       if showsWidgetLabel {
           Image("cat_full")
               .widgetLabel(label: Text("Cats"))
       }
       else {
           VStack {
               Image("cat_small")
               Text("Cats")
           }
       }
   }
}

```

这个环境值在为[doc://com.apple.documentation/documentation/WidgetKit/WidgetFamily/accessoryCircular] widget 系列定义外观时最有用，因为它的值可以根据 widget 出现的位置而改变。例如，如果 Widget 是 Infograph 表面最上方的圆形复杂功能，其值就是`true`。否则就是`false`。在 iOS 中，环境变量始终为 `false`。

其他系列则始终具有相同的值，与部件出现的位置无关。对于 [doc://com.apple.documentation/documentation/WidgetKit/WidgetFamily/accessoryCorner] widget 系列，该值始终为 `true`。对于其他系列，该值为`false`。

## 小工具

- **showsWidgetContainerBackground**：环境变量，用于指示是否显示 Widget 的背景。
- **widgetFamily**：窗口小部件的模板--小、中或大。
- **widgetRenderingMode**：部件的呈现模式，基于系统显示它的位置。
- **widgetContentMargins**：用于标识 widget 内容边距的属性。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/showsWidgetLabel
crawled: 2025-12-03T06:07:29Z
---

# showsWidgetLabel

**Instance Property**

A Boolean value that indicates whether an accessory family widget can display an accessory label.

## Declaration

```swift
var showsWidgetLabel: Bool { get set }
```

## Discussion

Use this value to determine if you can provide additional content, or possibly move some of the widget’s content out of the main view and into the widget label.

```swift

@Environment(\.widgetFamily) var widgetFamily
@Environment(\.showsWidgetLabel) var showsWidgetLabel

var body: some View {
   switch widgetFamily {
   case .accessoryCircular:
       if showsWidgetLabel {
           Image("cat_full")
               .widgetLabel(label: Text("Cats"))
       }
       else {
           VStack {
               Image("cat_small")
               Text("Cats")
           }
       }
   }
}

```

This environment value is most useful when defining the appearance for the [doc://com.apple.documentation/documentation/WidgetKit/WidgetFamily/accessoryCircular] widget family, because it’s value can change depending on where the widget appears. For example, if the widget is the top circular complication on the Infograph watch face, the value is `true`. Otherwise it is `false`. The environment variable is always `false` in iOS.

Other families always have the same value, regardless of where the widget appears. For the [doc://com.apple.documentation/documentation/WidgetKit/WidgetFamily/accessoryCorner] widget family, the value is always `true`. For other families, it is `false`.

## Widgets

- **showsWidgetContainerBackground**: An environment variable that indicates whether the background of a widget appears.
- **widgetFamily**: The template of the widget — small, medium, or large.
- **widgetRenderingMode**: The widget’s rendering mode, based on where the system is displaying it.
- **widgetContentMargins**: A property that identifies the content margins of a widget.

