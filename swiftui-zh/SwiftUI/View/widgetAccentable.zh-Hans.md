--- 来源：https://developer.apple.com/documentation/SwiftUI/View/widgetAccentable(_:)

抓取时间：2025-12-02T17:32:08Z

---

# widgetAccentable(_:)

**实例方法**

将视图及其所有子视图添加到强调组中。

## 声明

```swift
@MainActor @preconcurrency func widgetAccentable(_ accentable: Bool = true) -> some View

```

## 参数

- **accentable**：一个布尔值，指示是否将视图及其子视图添加到强调组中。

## 说明

当系统使用 `WidgetKit/WidgetRenderingMode/accented` 模式渲染组件时，它会将组件的视图层级结构分为两组：强调组和默认组。然后，它会为每个组应用不同的颜色。

应用颜色时，系统会将控件的视图视为模板图像。它会忽略视图本身的颜色，并根据视图的 Alpha 通道渲染新颜色。

要控制视图的外观，请将 `widgetAccentable(_:)` 修饰符添加到视图层级结构的一部分。如果 `accentable` 参数为 `true`，系统会将该视图及其所有子视图添加到强调组。所有其他视图则会被放入默认组。

```swift
var body: some View {
    VStack {
        Text("MON")
            .font(.caption)
            .widgetAccentable()
        Text("6")
            .font(.title)
        }
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/View/widgetAccentable(_:)
crawled: 2025-12-02T17:32:08Z
---

# widgetAccentable(_:)

**Instance Method**

Adds the view and all of its subviews to the accented group.

## Declaration

```swift
@MainActor @preconcurrency func widgetAccentable(_ accentable: Bool = true) -> some View

```

## Parameters

- **accentable**: A Boolean value that indicates whether to add the view and its subviews to the accented group.

## Discussion

When the system renders the widget using the `WidgetKit/WidgetRenderingMode/accented` mode, it divides the widget’s view hierarchy into two groups: the accented group and the default group. It then applies a different color to each group.

When applying the colors, the system treats the widget’s views as if they were template images. It ignores the view’s color — rendering the new colors based on the view’s alpha channel.

To control your view’s appearance, add the `widgetAccentable(_:)` modifier to part of your view’s hierarchy. If the `accentable` parameter is `true`, the system adds that view and all of its subviews to the accent group. It puts all other views in the default group.

```swift
var body: some View {
    VStack {
        Text("MON")
            .font(.caption)
            .widgetAccentable()
        Text("6")
            .font(.title)
        }
    }
}
```



