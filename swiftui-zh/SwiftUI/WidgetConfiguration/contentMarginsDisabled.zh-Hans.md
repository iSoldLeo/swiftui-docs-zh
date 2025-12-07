---
来源： https://developer.apple.com/documentation/SwiftUI/WidgetConfiguration/contentMarginsDisabled()
抓取时间： 2025-12-03T06:05:45Z
---

# contentMarginsDisabled()

**实例方法**

禁用默认内容边距。

## 声明

```swift
@MainActor @preconcurrency func contentMarginsDisabled() -> some WidgetConfiguration

```

## 返回值

修改后的不使用默认内容边距的 widget 配置。

## 讨论

如果禁用了 widget 的内容页边距，系统就不会自动在 widget 内容周围添加页边距，而是由您负责为每个上下文指定 widget 内容周围的页边距和填充。要指定自定义边距，请将[doc://com.apple.documentation/documentation/SwiftUI/EnvironmentValues/widgetContentMargins] 与[doc://com.apple.documentation/documentation/SwiftUI/View/padding(_:)] 结合使用，选择性地或部分地应用默认内容边距。

此修改器对 iOS 17、watchOS 10 或 macOS 14 之前的操作系统版本没有影响。

## 设置外观

- **supportedFamilies(_:)**：设置 widget 支持的尺寸。
- **disfavoredLocations(_:for:)**：设置 widget 不喜欢的位置。
- **containerBackgroundRemovable(_:)**：将 widget 的背景标记为可移动的修改器。


---
source: https://developer.apple.com/documentation/SwiftUI/WidgetConfiguration/contentMarginsDisabled()
crawled: 2025-12-03T06:05:45Z
---

# contentMarginsDisabled()

**Instance Method**

Disable default content margins.

## Declaration

```swift
@MainActor @preconcurrency func contentMarginsDisabled() -> some WidgetConfiguration

```

## Return Value

A modified widget configuration that doesn’t use default content margins.

## Discussion

When you disable content margins for a widget, the system doesn’t automatically add margins around the widget’s content, and you are responsible for specifying margins and padding around your widget content for each context. To specify custom margins, use [doc://com.apple.documentation/documentation/SwiftUI/EnvironmentValues/widgetContentMargins] in combination with [doc://com.apple.documentation/documentation/SwiftUI/View/padding(_:)] to selectively or partially apply the default content margins.

This modifier has no effect on operation system versions prior to iOS 17, watchOS 10, or macOS 14.

## Setting the appearance

- **supportedFamilies(_:)**: Sets the sizes that a widget supports.
- **disfavoredLocations(_:for:)**: Sets the disfavored locations for a widget.
- **containerBackgroundRemovable(_:)**: A modifier that marks the background of a widget as removable.

