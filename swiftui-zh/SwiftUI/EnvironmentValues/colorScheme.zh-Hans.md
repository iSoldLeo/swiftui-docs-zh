---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/colorScheme
抓取时间： 2025-12-02T17:32:44Z
---

# colorScheme

**实例属性**

该环境的配色方案。

## 声明

```swift
var colorScheme: ColorScheme { get set }
```

## 讨论

从视图中读取此环境值可了解 SwiftUI 当前是使用[light](../ColorScheme/light.zh-Hans.md) 还是[dark](../ColorScheme/dark.zh-Hans.md) 外观显示视图。您收到的值取决于用户是否启用了 "黑暗模式"，可能会被当前演示文稿视图层次结构的配置所取代。

```swift
@Environment(\.colorScheme) private var colorScheme

var body: some View {
    Text(colorScheme == .dark ? "Dark" : "Light")
}
```

您可以直接设置`colorScheme` 环境值，但这通常不是您想要的。这样做会改变给定视图及其子视图的配色方案，但不会**视图层次结构中其上层视图的配色方案。取而代之的是使用[preferredColorScheme(_:)](../View/preferredColorScheme.zh-Hans.md)修饰符来设置配色方案，这样也可以将该值通过视图层次结构向上传播到工作表或窗口等外层演示文稿。

在调整应用程序的用户界面以匹配配色方案时，也可考虑选中[colorSchemeContrast](colorSchemeContrast.zh-Hans.md) 属性，它反映了由用户控制的全系统对比度设置。有关信息，请参阅《人机界面指南》中的 [doc://com.apple.documentation/design/Human-Interface-Guidelines/accessibility#Color-and-effects]。



## 检测和请求明暗外观

- **preferredColorScheme(_:)**：设置此演示文稿的首选配色方案。
- **ColorScheme**：可能的配色方案，分别对应亮色和暗色外观。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/colorScheme
crawled: 2025-12-02T17:32:44Z
---

# colorScheme

**Instance Property**

The color scheme of this environment.

## Declaration

```swift
var colorScheme: ColorScheme { get set }
```

## Discussion

Read this environment value from within a view to find out if SwiftUI is currently displaying the view using the [light](../ColorScheme/light.zh-Hans.md) or [dark](../ColorScheme/dark.zh-Hans.md) appearance. The value that you receive depends on whether the user has enabled Dark Mode, possibly superseded by the configuration of the current presentation’s view hierarchy.

```swift
@Environment(\.colorScheme) private var colorScheme

var body: some View {
    Text(colorScheme == .dark ? "Dark" : "Light")
}
```

You can set the `colorScheme` environment value directly, but that usually isn’t what you want. Doing so changes the color scheme of the given view and its child views but *not* the views above it in the view hierarchy. Instead, set a color scheme using the [preferredColorScheme(_:)](../View/preferredColorScheme.zh-Hans.md) modifier, which also propagates the value up through the view hierarchy to the enclosing presentation, like a sheet or a window.

When adjusting your app’s user interface to match the color scheme, consider also checking the [colorSchemeContrast](colorSchemeContrast.zh-Hans.md) property, which reflects a system-wide contrast setting that the user controls. For information, see [doc://com.apple.documentation/design/Human-Interface-Guidelines/accessibility#Color-and-effects] in the Human Interface Guidelines.



## Detecting and requesting the light or dark appearance

- **preferredColorScheme(_:)**: Sets the preferred color scheme for this presentation.
- **ColorScheme**: The possible color schemes, corresponding to the light and dark appearances.

