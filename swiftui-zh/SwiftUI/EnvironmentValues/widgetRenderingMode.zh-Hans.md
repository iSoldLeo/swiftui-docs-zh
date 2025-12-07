---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/widgetRenderingMode
抓取时间： 2025-12-03T06:07:32Z
---

# 小部件渲染模式

**实例属性**

部件的渲染模式，基于系统显示该部件的位置。

## 声明

```swift
var widgetRenderingMode: WidgetRenderingMode { get set }
```

## 讨论

使用此键可以从环境值中读取渲染模式。

```swift
@Environment(\.widgetRenderingMode) var widgetRenderingMode
```

然后根据模式修改 widget 的外观。

```swift
var body: some View {
    ZStack {
       switch renderingMode {
        case .fullColor:
           Text("Full color")
        case .accented:
           ZStack {
               Circle(...)
               VStack {
                   Text("Accented")
                       .widgetAccentable()
                   Text("Normal")
               }
           }
        case .vibrant:
           Text("Full color")
        default:
           ...
        }
    }
}
```

## 小工具

- **showsWidgetContainerBackground**：环境变量，用于指示是否显示 Widget 的背景。
- **showsWidgetLabel**：布尔值，用于指示附件系列 widget 是否可以显示附件标签。
- **widgetFamily**：部件的模板 - 小、中或大。
- **widgetContentMargins**：用于标识 widget 内容边距的属性。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/widgetRenderingMode
crawled: 2025-12-03T06:07:32Z
---

# widgetRenderingMode

**Instance Property**

The widget’s rendering mode, based on where the system is displaying it.

## Declaration

```swift
var widgetRenderingMode: WidgetRenderingMode { get set }
```

## Discussion

You can read the rendering mode from the environment values using this key.

```swift
@Environment(\.widgetRenderingMode) var widgetRenderingMode
```

Then modify the widget’s appearance based on the mode.

```swift
var body: some View {
    ZStack {
       switch renderingMode {
        case .fullColor:
           Text("Full color")
        case .accented:
           ZStack {
               Circle(...)
               VStack {
                   Text("Accented")
                       .widgetAccentable()
                   Text("Normal")
               }
           }
        case .vibrant:
           Text("Full color")
        default:
           ...
        }
    }
}
```

## Widgets

- **showsWidgetContainerBackground**: An environment variable that indicates whether the background of a widget appears.
- **showsWidgetLabel**: A Boolean value that indicates whether an accessory family widget can display an accessory label.
- **widgetFamily**: The template of the widget — small, medium, or large.
- **widgetContentMargins**: A property that identifies the content margins of a widget.

