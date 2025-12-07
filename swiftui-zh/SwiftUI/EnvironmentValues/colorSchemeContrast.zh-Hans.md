---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/colorSchemeContrast
抓取时间： 2025-12-02T17:32:46Z
---

# colorSchemeContrast

**实例属性**

与此环境配色方案相关的对比度。

## 声明

```swift
var colorSchemeContrast: ColorSchemeContrast { get }
```

## 讨论

从视图中读取此环境值，以了解 SwiftUI 当前是使用[standard](../ColorSchemeContrast/standard.zh-Hans.md) 还是[increased](../ColorSchemeContrast/increased.zh-Hans.md) 对比度来显示视图。您读取的值完全取决于用户设置，无法更改。

```swift
@Environment(\.colorSchemeContrast) private var colorSchemeContrast

var body: some View {
    Text(colorSchemeContrast == .standard ? "Standard" : "Increased")
}
```

在调整应用程序的用户界面以匹配对比度时，还可以考虑检查[colorScheme](colorScheme.zh-Hans.md) 属性，以了解 SwiftUI 是否以浅色或深色外观显示视图。有关信息，请参阅《人机界面指南》中的[doc://com.apple.documentation/design/Human-Interface-Guidelines/accessibility#Color-and-effects]。



## 获取配色方案对比度

- **ColorSchemeContrast**：应用程序前景色和背景色的对比度。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/colorSchemeContrast
crawled: 2025-12-02T17:32:46Z
---

# colorSchemeContrast

**Instance Property**

The contrast associated with the color scheme of this environment.

## Declaration

```swift
var colorSchemeContrast: ColorSchemeContrast { get }
```

## Discussion

Read this environment value from within a view to find out if SwiftUI is currently displaying the view using [standard](../ColorSchemeContrast/standard.zh-Hans.md) or [increased](../ColorSchemeContrast/increased.zh-Hans.md) contrast. The value that you read depends entirely on user settings, and you can’t change it.

```swift
@Environment(\.colorSchemeContrast) private var colorSchemeContrast

var body: some View {
    Text(colorSchemeContrast == .standard ? "Standard" : "Increased")
}
```

When adjusting your app’s user interface to match the contrast, consider also checking the [colorScheme](colorScheme.zh-Hans.md) property to find out if SwiftUI is displaying the view with a light or dark appearance. For information, see [doc://com.apple.documentation/design/Human-Interface-Guidelines/accessibility#Color-and-effects] in the Human Interface Guidelines.



## Getting the color scheme contrast

- **ColorSchemeContrast**: The contrast between the app’s foreground and background colors.

