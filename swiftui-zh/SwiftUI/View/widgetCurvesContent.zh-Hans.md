--- 来源：https://developer.apple.com/documentation/SwiftUI/View/widgetCurvesContent(_:)

抓取时间：2025-12-01T10:22:55Z

---

# widgetCurvesContent(_:)

**实例方法**

如果上下文允许，则沿曲线显示组件内容。

## 声明

```swift
@MainActor @preconcurrency func widgetCurvesContent(_ curvesContent: Bool = true) -> some View

```

## 参数

- **curvesContent**：一个布尔值，指示系统是否在上下文允许的情况下使组件标签的内容弯曲。

## 说明

当显示 [doc://com.apple.documentation/documentation/WidgetKit/WidgetFamily/accessoryCorner] 复杂功能时，系统会将组件内容沿表盘拐角处的曲线定位。该组件必须使用 [doc://com.apple.documentation/documentation/SwiftUI/View/widgetLabel(_:)-7wguh] 修饰符，并且弯曲效果仅修改文本、SF 符号和图像。

显示 `.accessoryCorner` 复杂组件时，系统会将组件标签放置在曲线内侧，组件内容放置在曲线外侧，如下图所示。

```swift
var body: some View {
    Text("Hi")
        .widgetCurvesContent()
        .widgetLabel("World!")
}
```

系统还可以对 [doc://com.apple.documentation/documentation/SwiftUI/ViewThatFits] 视图中的文本、SF 符号和图像内容进行弯曲处理。

```swift
var body: some View {
    ViewThatFits {
        Text("Hello")
        Text("Hi")
    }
    .widgetCurvesContent()
    .widgetLabel("World!")
}
```

## 组件配置

- **widgetAccentable(_:)**：将视图及其所有子视图添加到强调组中。

- **widgetLabel(_:)**：返回一个本地化的文本标签，用于在附件组件的主 SwiftUI 视图之外显示附加内容。

- **widgetLabel(label:)**：创建一个标签，用于在配件系列组件的主 SwiftUI 视图之外显示附加内容。

- **dynamicIsland(verticalPlacement:)**：指定动态岛中展开的 Live Activity 视图的垂直位置。

- **accessoryWidgetGroupStyle(_:)**：可应用于 `AccessoryWidgetGroup` 的视图修饰符，用于指定三个内容视图的遮罩形状。`style` 的值设置为 `.automatic`，其默认值为 `.circular`。


---
source: https://developer.apple.com/documentation/SwiftUI/View/widgetCurvesContent(_:)
crawled: 2025-12-01T10:22:55Z
---

# widgetCurvesContent(_:)

**Instance Method**

Displays the widget’s content along a curve if the context allows it.

## Declaration

```swift
@MainActor @preconcurrency func widgetCurvesContent(_ curvesContent: Bool = true) -> some View

```

## Parameters

- **curvesContent**: A Boolean value that indicates whether the system curves the widget label’s content, if the context allows.

## Discussion

The system positions the widget’s content along a curve that follows the corner of the watch face when displaying a [doc://com.apple.documentation/documentation/WidgetKit/WidgetFamily/accessoryCorner] complication. The widget must use  a  [doc://com.apple.documentation/documentation/SwiftUI/View/widgetLabel(_:)-7wguh] modifier, and the curving effect modifies only text, SF Symbols, and images.

When displaying an `.accessoryCorner` complication, the system places the widget label on the inside of the curve, and the widget’s content on the outside, as shown below.

```swift
var body: some View {
    Text("Hi")
        .widgetCurvesContent()
        .widgetLabel("World!")
}
```



The system can also curve text, SF symbols, and image content from a [doc://com.apple.documentation/documentation/SwiftUI/ViewThatFits] view.

```swift
var body: some View {
    ViewThatFits {
        Text("Hello")
        Text("Hi")
    }
    .widgetCurvesContent()
    .widgetLabel("World!")
}
```



## Widget configuration

- **widgetAccentable(_:)**: Adds the view and all of its subviews to the accented group.
- **widgetLabel(_:)**: Returns a localized text label that displays additional content outside the accessory family widget’s main SwiftUI view.
- **widgetLabel(label:)**: Creates a label for displaying additional content outside an accessory family widget’s main SwiftUI view.
- **dynamicIsland(verticalPlacement:)**: Specifies the vertical placement for a view of an expanded Live Activity that appears in the Dynamic Island.
- **accessoryWidgetGroupStyle(_:)**: The view modifier that can be applied to `AccessoryWidgetGroup` to specify the shape the three content views will be masked with. The value of `style` is set to `.automatic`, which is `.circular` by default.

