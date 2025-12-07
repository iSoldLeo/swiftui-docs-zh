---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/widgetContentMargins
抓取时间： 2025-12-03T06:07:32Z
---

# widgetContentMargins

**实例属性**

用于标识 widget 内容边距的属性。

## 声明

```swift
var widgetContentMargins: EdgeInsets { get }
```

## 返回值

返回当前 widget 演示上下文的内容边距。

## 讨论

widget 的内容页边距取决于其显示的上下文。系统会应用默认的内容页边距。但是，如果您使用[doc://com.apple.documentation/documentation/SwiftUI/WidgetConfiguration/contentMarginsDisabled()]禁用了自动应用默认内容边距的功能，系统就会结合`widgetContentMargins`属性和[doc://com.apple.documentation/documentation/SwiftUI/View/padding(_:)]有选择地应用默认内容边距。

## 小工具

- **showsWidgetContainerBackground**：环境变量，用于指示是否显示 Widget 的背景。
- **showsWidgetLabel**：布尔值，用于指示附件系列 widget 是否可以显示附件标签。
- **widgetFamily**：部件的模板--小号、中号或大号。
- **widgetRenderingMode**：窗口小部件的呈现模式，取决于系统显示窗口小部件的位置。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/widgetContentMargins
crawled: 2025-12-03T06:07:32Z
---

# widgetContentMargins

**Instance Property**

A property that identifies the content margins of a widget.

## Declaration

```swift
var widgetContentMargins: EdgeInsets { get }
```

## Return Value

Returns the content margins for the current widget presentation context.

## Discussion

The content margins of a widget depend on the context in which it appears. The system applies default content margins. However, if you disable automatic application of default content margins with [doc://com.apple.documentation/documentation/SwiftUI/WidgetConfiguration/contentMarginsDisabled()], the system uses the `widgetContentMargins` property in combination with [doc://com.apple.documentation/documentation/SwiftUI/View/padding(_:)] to selectively apply default content margins.

## Widgets

- **showsWidgetContainerBackground**: An environment variable that indicates whether the background of a widget appears.
- **showsWidgetLabel**: A Boolean value that indicates whether an accessory family widget can display an accessory label.
- **widgetFamily**: The template of the widget — small, medium, or large.
- **widgetRenderingMode**: The widget’s rendering mode, based on where the system is displaying it.

