--- 来源：https://developer.apple.com/documentation/SwiftUI/ColorPicker/init(_:selection:supportsOpacity:)

抓取时间：2025-12-03T05:40:13Z

---

# init(_:selection:supportsOpacity:)

**Initializer**

创建一个颜色选择器，其文本标签由标题字符串键生成。

## 声明

```swift
nonisolated init(_ titleKey: LocalizedStringKey, selection: Binding<CGColor>, supportsOpacity: Bool = true)
```

## 参数

- **titleKey**：选择器本地化标题的键。

- **selection**：指向显示所选颜色的变量的 [Binding](../Binding.zh-Hans.md) 值。

- **supportsOpacity**：一个布尔值，指示颜色选择器是否允许调整所选颜色的不透明度；默认值为 `true`。

## 创建颜色选择器

- **init(selection:supportsOpacity:label:)**：创建一个用于选择颜色的实例。


---
source: https://developer.apple.com/documentation/SwiftUI/ColorPicker/init(_:selection:supportsOpacity:)
crawled: 2025-12-03T05:40:13Z
---

# init(_:selection:supportsOpacity:)

**Initializer**

Creates a color picker with a text label generated from a title string key.

## Declaration

```swift
nonisolated init(_ titleKey: LocalizedStringKey, selection: Binding<CGColor>, supportsOpacity: Bool = true)
```

## Parameters

- **titleKey**: The key for the localized title of the picker.
- **selection**: A [Binding](../Binding.zh-Hans.md) to the variable that displays the selected `CGColor`.
- **supportsOpacity**: A Boolean value that indicates whether the color picker allows adjustments to the selected color’s opacity; the default is `true`.

## Creating a color picker

- **init(selection:supportsOpacity:label:)**: Creates an instance that selects a color.

