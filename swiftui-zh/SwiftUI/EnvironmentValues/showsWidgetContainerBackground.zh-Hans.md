---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/showsWidgetContainerBackground
抓取时间：2025-12-03T06:07:29Z
---

# showsWidgetContainerBackground

**实例属性**

环境变量，用于指示是否显示 widget 的背景。

## 声明

```swift
var showsWidgetContainerBackground: Bool { get }
```

## 返回值

`true` 如果默认情况下背景显示在此上下文中；否则为 `false`。

## 讨论

在 iOS 16 及更早版本中，系统部件的环境变量始终为 `true`，附件部件的环境变量始终为 `false`。在 macOS 13 及更早版本和 watchOS 9 及更早版本中，它的值总是`true`。

如果将`false`传递给[doc://com.apple.documentation/documentation/SwiftUI/WidgetConfiguration/containerBackgroundRemovable(_:)]以始终显示 widget 背景，即使`showsWidgetContainerBackground`的评估值为`true`，系统也会显示 widget 背景。

## 小工具

- **showsWidgetLabel**：布尔值，表示附件系列 Widget 是否可以显示附件标签。
- **widgetFamily**：部件的模板--小号、中号或大号。
- **widgetRenderingMode**：部件的呈现模式，基于系统显示它的位置。
- **widgetContentMargins**：用于标识 widget 内容边距的属性。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/showsWidgetContainerBackground
crawled: 2025-12-03T06:07:29Z
---

# showsWidgetContainerBackground

**Instance Property**

An environment variable that indicates whether the background of a widget appears.

## Declaration

```swift
var showsWidgetContainerBackground: Bool { get }
```

## Return Value

`true` if, by default, the background appears in this context; `false` otherwise.

## Discussion

In iOS 16 and earlier, this environment variable is always `true` for system widgets and `false` for accessory widgets. In macOS 13 and earlier, and in watchOS 9 and earlier, it always evaluates to `true`.

If you pass `false` to [doc://com.apple.documentation/documentation/SwiftUI/WidgetConfiguration/containerBackgroundRemovable(_:)] to always show the widget background, the system shows the widget background even if `showsWidgetContainerBackground` evaluates to `true`.

## Widgets

- **showsWidgetLabel**: A Boolean value that indicates whether an accessory family widget can display an accessory label.
- **widgetFamily**: The template of the widget — small, medium, or large.
- **widgetRenderingMode**: The widget’s rendering mode, based on where the system is displaying it.
- **widgetContentMargins**: A property that identifies the content margins of a widget.

