--- 来源：https://developer.apple.com/documentation/SwiftUI/ColorPicker/init(selection:supportsOpacity:label:)

抓取时间：2025-12-01T10:29:23Z

---

# init(selection:supportsOpacity:label:)

**Initializer**

创建一个用于选择颜色的实例。

## 声明

```swift
init(selection: Binding<CGColor>, supportsOpacity: Bool = true, @ViewBuilder label: () -> Label)
```

## 参数

- **selection**：一个指向用于显示所选颜色的变量的 [Binding](../Binding.zh-Hans.md) 值。`CGColor`

- **supportsOpacity**：一个布尔值，指示颜色选择器是否允许调整所选颜色的不透明度；默认值为 `true`。

- **label**：描述所选颜色用途的视图。系统颜色选择器 UI 会使用此视图中的文本设置其标题。

## 创建颜色选择器

- **init(_:selection:supportsOpacity:)**：创建一个颜色选择器，其文本标签由标题字符串键生成。


---
source: https://developer.apple.com/documentation/SwiftUI/ColorPicker/init(selection:supportsOpacity:label:)
crawled: 2025-12-01T10:29:23Z
---

# init(selection:supportsOpacity:label:)

**Initializer**

Creates an instance that selects a color.

## Declaration

```swift
init(selection: Binding<CGColor>, supportsOpacity: Bool = true, @ViewBuilder label: () -> Label)
```

## Parameters

- **selection**: A [Binding](../Binding.zh-Hans.md) to the variable that displays the selected `CGColor`.
- **supportsOpacity**: A Boolean value that indicates whether the color picker allows adjusting the selected color’s opacity; the default is `true`.
- **label**: A view that describes the use of the selected color. The system color picker UI sets it’s title using the text from this view.

## Creating a color picker

- **init(_:selection:supportsOpacity:)**: Creates a color picker with a text label generated from a title string key.

