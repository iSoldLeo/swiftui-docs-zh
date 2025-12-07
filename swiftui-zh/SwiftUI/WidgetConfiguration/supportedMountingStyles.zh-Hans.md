---
来源： https://developer.apple.com/documentation/SwiftUI/WidgetConfiguration/supportedMountingStyles(_:)
抓取时间： 2025-12-03T04:06:12Z
---

# supportedMountingStyles(_:)

**实例方法**

指定此 widget 的安装样式。

## 声明

```swift
@MainActor @preconcurrency func supportedMountingStyles(_ styles: [WidgetMountingStyle]) -> some WidgetConfiguration

```

## 参数

- **styles**：widget 支持的安装样式集。

## 返回值

支持指定安装方式的 widget 配置。

## 讨论

安装样式视图修改器只对 visionOS 中的部件有效，包括兼容 iOS 或 iPadOS 应用程序的兼容部件。

```swift
struct MySpatialWidget: Widget {
     let kind: String = "MySpatialWidget"

     var body: some WidgetConfiguration {
         AppIntentConfiguration(kind: kind, intent: ConfigurationIntent.self, provider: Provider()) { entry in
             EntryView(entry: entry)
                .containerBackground(.fill.tertiary, for: .widget)
         }
         .supportedFamilies([.systemSmall, .systemLarge])
         .supportedMountingStyles([.recessed])
     }
}
```

上述代码定义了一个仅支持嵌入式安装样式的 widget。

安装样式视图修改器只对 visionOS 中的部件有效，包括兼容 iOS 或 iPadOS 应用程序的兼容部件。


---
source: https://developer.apple.com/documentation/SwiftUI/WidgetConfiguration/supportedMountingStyles(_:)
crawled: 2025-12-03T04:06:12Z
---

# supportedMountingStyles(_:)

**Instance Method**

Specifies the mounting style for this widget.

## Declaration

```swift
@MainActor @preconcurrency func supportedMountingStyles(_ styles: [WidgetMountingStyle]) -> some WidgetConfiguration

```

## Parameters

- **styles**: The set of mounting styles that the widget supports.

## Return Value

A widget configuration that supports the specified mounting styles.

## Discussion

The mounting style view modifier only has an effect to widgets in visionOS, including widgets of compatible widgets of compatible iOS or iPadOS apps.

```swift
struct MySpatialWidget: Widget {
     let kind: String = "MySpatialWidget"

     var body: some WidgetConfiguration {
         AppIntentConfiguration(kind: kind, intent: ConfigurationIntent.self, provider: Provider()) { entry in
             EntryView(entry: entry)
                .containerBackground(.fill.tertiary, for: .widget)
         }
         .supportedFamilies([.systemSmall, .systemLarge])
         .supportedMountingStyles([.recessed])
     }
}
```

The above code defines a widget that only supports the recessed mounting style.

The mounting style view modifier only has an effect to widgets in visionOS, including widgets of compatible widgets of compatible iOS or iPadOS apps.

