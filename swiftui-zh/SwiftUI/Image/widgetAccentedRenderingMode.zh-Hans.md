---
来源： https://developer.apple.com/documentation/SwiftUI/Image/widgetAccentedRenderingMode(_:)
抓取时间： 2025-12-03T04:29:17Z
---

# widgetAccentedRenderingMode(_:)

**实例方法**

指定在使用`Image` 模式时如何渲染`WidgetKit/WidgetRenderingMode/accented`。

## 声明

```swift
func widgetAccentedRenderingMode(_ renderingMode: WidgetAccentedRenderingMode?) -> some View

```

## 参数

- **renderingMode**：描述`Image` 应如何渲染的常量。

## 讨论

```swift
var body: some View {
    VStack {
        Image("cat_full")
            .resizable()
            .widgetAccentedRenderingMode(.fullColor)
    }
}
```




---
source: https://developer.apple.com/documentation/SwiftUI/Image/widgetAccentedRenderingMode(_:)
crawled: 2025-12-03T04:29:17Z
---

# widgetAccentedRenderingMode(_:)

**Instance Method**

Specifies the how to render an `Image` when using the `WidgetKit/WidgetRenderingMode/accented` mode.

## Declaration

```swift
func widgetAccentedRenderingMode(_ renderingMode: WidgetAccentedRenderingMode?) -> some View

```

## Parameters

- **renderingMode**: A constant describing how the `Image` should be rendered.

## Discussion

```swift
var body: some View {
    VStack {
        Image("cat_full")
            .resizable()
            .widgetAccentedRenderingMode(.fullColor)
    }
}
```



