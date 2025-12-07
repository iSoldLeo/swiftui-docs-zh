---
来源： https://developer.apple.com/documentation/SwiftUI/PickerStyle/palette
抓取时间： 2025-12-03T06:09:18Z
---

# 调色板

**类型属性**

一种拾取器样式，可将选项显示为一排紧凑的元素。

## 声明

```swift
static var palette: PalettePickerStyle { get }
```

## 讨论



如果添加的选项超过 6 个，在 iOS 上选择器会水平滚动。

下面的示例创建了一个调色板拾取器：

```swift
enum Reaction: Identifiable, CaseIterable {
    case thumbsup, thumbsdown, heart, questionMark
    var id: Self { self }
}

@State private var selection: Reaction? = .none

var body: some View {
    Menu("Reactions") {
        Picker("Palette", selection: $selection) {
            Label("Thumbs up", systemImage: "hand.thumbsup")
                .tag(Reaction.thumbsup)
            Label("Thumbs down", systemImage: "hand.thumbsdown")
                .tag(Reaction.thumbsdown)
            Label("Like", systemImage: "heart")
                .tag(Reaction.heart)
            Label("Question mark", systemImage: "questionmark")
                .tag(Reaction.questionMark)
        }
        .pickerStyle(.palette)
        Button("Reply...") { ... }
    }
}
```

调色板选择器将通过应用系统色调来显示未着色 SF 符号或模板图像的选择。对于着色 SF 符号，在选择时会在符号周围勾勒出一条线。如果您想提供特定图像（或 SF 符号）来表示选择，建议使用 [custom](../PaletteSelectionEffect/custom.zh-Hans.md)。这将停用任何系统选择行为，允许所提供的图像单独表示选择。

下面的示例创建了一个调色板选择器，禁用了系统选择行为：

```swift
Menu {
    Picker("Palettes", selection: $selection) {
        ForEach(palettes) { palette in
            Label(palette.title, systemImage: selection == palette ?
                  "circle.dashed.inset.filled" : "circle.fill")
            .tint(palette.tint)
            .tag(palette)
        }
    }
    .pickerStyle(.palette)
    .paletteSelectionEffect(.custom)
} label: {
    ...
}
```

如果希望使用特定的 SF 符号变量，请使用 [symbolVariant(_:)](../PaletteSelectionEffect/symbolVariant.zh-Hans.md)：

```swift
Menu {
    Picker("Flags", selection: $selectedFlag) {
        ForEach(flags) { flag in
            Label(flag.title, systemImage: "flag")
                .tint(flag.color)
                .tag(flag)
        }
    }
    .pickerStyle(.palette)
    .paletteSelectionEffect(.symbolVariant(.slash))
} label: {
    ...
}
```

要将此样式应用于选取器或包含选取器的视图，请使用[pickerStyle(_:)](../View/pickerStyle.zh-Hans.md)修饰符。

## 获取内置拾取器样式

- **automatic**：基于选取器上下文的默认选取器样式。
- **inline**：一个 `PickerStyle`，其中每个选项都与当前容器中的其他视图并列显示。
- **menu**：选取器样式，当用户按下按钮时，以菜单的形式显示选项，当嵌套在较大的菜单中时，则以子菜单的形式显示选项。
- **navigationLink**：由导航链接表示的选取器样式，通过推动列表样式的选取器视图来显示选项。
- **radioGroup**：以一组单选按钮显示选项的选取器样式。
- **segmented**：在分段控件中显示选项的选取器样式。
- **wheel**：一种选取器样式，它以可滚动滚轮的方式显示选项，滚轮上显示所选选项和邻近的几个选项。


---
source: https://developer.apple.com/documentation/SwiftUI/PickerStyle/palette
crawled: 2025-12-03T06:09:18Z
---

# palette

**Type Property**

A picker style that presents the options as a row of compact elements.

## Declaration

```swift
static var palette: PalettePickerStyle { get }
```

## Discussion



For each option’s label, use one symbol per item, if you add more than 6 options, the picker scrolls horizontally on iOS.

The following example creates a palette picker:

```swift
enum Reaction: Identifiable, CaseIterable {
    case thumbsup, thumbsdown, heart, questionMark
    var id: Self { self }
}

@State private var selection: Reaction? = .none

var body: some View {
    Menu("Reactions") {
        Picker("Palette", selection: $selection) {
            Label("Thumbs up", systemImage: "hand.thumbsup")
                .tag(Reaction.thumbsup)
            Label("Thumbs down", systemImage: "hand.thumbsdown")
                .tag(Reaction.thumbsdown)
            Label("Like", systemImage: "heart")
                .tag(Reaction.heart)
            Label("Question mark", systemImage: "questionmark")
                .tag(Reaction.questionMark)
        }
        .pickerStyle(.palette)
        Button("Reply...") { ... }
    }
}
```

Palette pickers will display the selection of untinted SF Symbols or template images by applying the system tint. For tinted SF Symbols, a stroke is outlined around the symbol upon selection. If you would like to supply a particular image (or SF Symbol) to signify selection, we suggest using [custom](../PaletteSelectionEffect/custom.zh-Hans.md). This deactivates any system selection behavior, allowing the provided image to solely indicate selection instead.

The following example creates a palette picker that disables the system selection behaviour:

```swift
Menu {
    Picker("Palettes", selection: $selection) {
        ForEach(palettes) { palette in
            Label(palette.title, systemImage: selection == palette ?
                  "circle.dashed.inset.filled" : "circle.fill")
            .tint(palette.tint)
            .tag(palette)
        }
    }
    .pickerStyle(.palette)
    .paletteSelectionEffect(.custom)
} label: {
    ...
}
```

If a specific SF Symbol variant is preferable instead, use [symbolVariant(_:)](../PaletteSelectionEffect/symbolVariant.zh-Hans.md):

```swift
Menu {
    Picker("Flags", selection: $selectedFlag) {
        ForEach(flags) { flag in
            Label(flag.title, systemImage: "flag")
                .tint(flag.color)
                .tag(flag)
        }
    }
    .pickerStyle(.palette)
    .paletteSelectionEffect(.symbolVariant(.slash))
} label: {
    ...
}
```

To apply this style to a picker, or to a view that contains pickers, use the [pickerStyle(_:)](../View/pickerStyle.zh-Hans.md) modifier.

## Getting built-in picker styles

- **automatic**: The default picker style, based on the picker’s context.
- **inline**: A `PickerStyle` where each option is displayed inline with other views in the current container.
- **menu**: A picker style that presents the options as a menu when the user presses a button, or as a submenu when nested within a larger menu.
- **navigationLink**: A picker style represented by a navigation link that presents the options by pushing a List-style picker view.
- **radioGroup**: A picker style that presents the options as a group of radio buttons.
- **segmented**: A picker style that presents the options in a segmented control.
- **wheel**: A picker style that presents the options in a scrollable wheel that shows the selected option and a few neighboring options.

