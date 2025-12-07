--- 来源：https://developer.apple.com/documentation/SwiftUI/ColorPicker
抓取时间：2025-12-02T17:26:42Z

---

# ColorPicker

**Structure**

用于从系统颜色选择器界面选择颜色的控件。

## 声明

```swift
struct ColorPicker<Label> where Label : View
```

## 概述

颜色选择器显示当前选中的颜色，并显示更大的系统颜色选择器，以便用户选择新颜色。

默认情况下，颜色选择器支持带透明度的颜色；要禁用透明度支持，请将 `supportsOpacity` 参数设置为 `false`。在此模式下，颜色选择器将不会显示用于调整所选颜色透明度的控件，并且会移除通过编程方式设置或从用户系统收藏夹中选择的任何颜色的透明度。

您可以通过将 `ColorPicker` 嵌入视图层级结构中，并使用标题字符串和 [Binding](Binding.zh-Hans.md) 初始化它，将其转换为 [Color](Color.zh-Hans.md)：

```swift
struct FormattingControls: View {
    @State private var bgColor =
        Color(.sRGB, red: 0.98, green: 0.9, blue: 0.2)

    var body: some View {
        VStack {
            ColorPicker("Alignment Guides", selection: $bgColor)
        }
    }
}
```

## 创建颜色选择器

- **init(_:selection:supportsOpacity:)**：创建一个颜色选择器，其文本标签由标题字符串键生成。

- **init(selection:supportsOpacity:label:)**：创建一个用于选择颜色的实例。

## 符合以下规范

- 视图


---
source: https://developer.apple.com/documentation/SwiftUI/ColorPicker
crawled: 2025-12-02T17:26:42Z
---

# ColorPicker

**Structure**

A control used to select a color from the system color picker UI.

## Declaration

```swift
struct ColorPicker<Label> where Label : View
```

## Overview

The color picker shows the currently selected color and displays the larger system color picker that allows people to select a new color.

By default color picker supports colors with opacity; to disable opacity support, set the `supportsOpacity` parameter to `false`. In this mode the color picker won’t show controls for adjusting the opacity of the selected color, and strips out opacity from any color set programmatically or selected from the user’s system favorites.

You use `ColorPicker` by embedding it inside a view hierarchy and initializing it with a title string and a [Binding](Binding.zh-Hans.md) to a [Color](Color.zh-Hans.md):

```swift
struct FormattingControls: View {
    @State private var bgColor =
        Color(.sRGB, red: 0.98, green: 0.9, blue: 0.2)

    var body: some View {
        VStack {
            ColorPicker("Alignment Guides", selection: $bgColor)
        }
    }
}
```

## Creating a color picker

- **init(_:selection:supportsOpacity:)**: Creates a color picker with a text label generated from a title string key.
- **init(selection:supportsOpacity:label:)**: Creates an instance that selects a color.

## Conforms To

- View

