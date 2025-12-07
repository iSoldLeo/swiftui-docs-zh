---
来源： https://developer.apple.com/documentation/SwiftUI/WidgetConfiguration/widgetTexture(_:)
抓取时间： 2025-12-03T04:06:10Z
---

# widgetTexture(_:)

**实例方法**

指定此 widget 的纹理。

## 声明

```swift
@MainActor @preconcurrency func widgetTexture(_ material: WidgetTexture) -> some WidgetConfiguration

```

## 返回值

使用指定 widget 纹理的 widget 配置。

## 讨论

visionOS 中的 widget 都会应用材质处理。默认情况下，所有部件都使用 `glass` 部件纹理。使用此修改器可为部件明确设置部件纹理。

下面显示一个纹理为纸张的 widget：

```swift
AppIntentConfiguration(
    kind: kind, intent: LatestPostConfiguration.self, provider: Provider()
) { entry in
    LatestPostsView(entry: entry)
}
.widgetTexture(.paper)
```


---
source: https://developer.apple.com/documentation/SwiftUI/WidgetConfiguration/widgetTexture(_:)
crawled: 2025-12-03T04:06:10Z
---

# widgetTexture(_:)

**Instance Method**

Specifies the widget texture for this widget.

## Declaration

```swift
@MainActor @preconcurrency func widgetTexture(_ material: WidgetTexture) -> some WidgetConfiguration

```

## Return Value

A widget configuration using the specified widget texture.

## Discussion

Widgets in visionOS use a have a material treatment applied. By default, all widgets use the `glass` widget texture. Use this modifier to explicitly set the widget texture for a widget.

The following displays a widget whose texture is paper:

```swift
AppIntentConfiguration(
    kind: kind, intent: LatestPostConfiguration.self, provider: Provider()
) { entry in
    LatestPostsView(entry: entry)
}
.widgetTexture(.paper)
```

