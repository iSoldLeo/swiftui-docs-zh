--- 来源：https://developer.apple.com/documentation/SwiftUI/ControlGroupStyle/palette
抓取时间：2025-12-03T06:11:30Z

---

# 调色板

**类型属性**

一种控件组样式，将其内容呈现为调色板。

## 声明

```swift
@MainActor @preconcurrency static var palette: PaletteControlGroupStyle { get }
```

## 讨论

使用此样式可以渲染多选调色板或无状态调色板。以下示例创建了一个包含这两种类型搁架的控件组：

```swift
Menu {
    // A multi select palette
    ControlGroup {
        ForEach(ColorTags.allCases) { colorTag in
            Toggle(isOn: $selectedColorTags[colorTag]) {
                Label(colorTag.name, systemImage: "circle")
            }
            .tint(colorTag.color)
        }
    }
    .controlGroupStyle(.palette)
    .paletteSelectionEffect(.symbolVariant(.fill))

    // A momentary / stateless palette
    ControlGroup {
        ForEach(Emotes.allCases) { emote in
            Button {
                sendEmote(emote)
            } label: {
                Label(emote.name, systemImage: emote.systemImage)
            }
        }
    }
    .controlGroupStyle(.palette)
}
```

要将此样式应用于控件组或包含控件组的视图，请使用 [controlGroupStyle(_:)](../View/controlGroupStyle.zh-Hans.md) 修饰符。

## 获取内置控件组样式

- **automatic**：默认控件组样式。

- **compactMenu**：一种控件组样式，当用户按下控件时，其内容以紧凑菜单的形式呈现；当嵌套在更大的菜单中时，则以子菜单的形式呈现。

- **menu**：一种控件组样式，当用户按下控件时，其内容以菜单的形式呈现；当嵌套在更大的菜单中时，则以子菜单的形式呈现。

- **navigation**：导航控件组样式。


---
source: https://developer.apple.com/documentation/SwiftUI/ControlGroupStyle/palette
crawled: 2025-12-03T06:11:30Z
---

# palette

**Type Property**

A control group style that presents its content as a palette.

## Declaration

```swift
@MainActor @preconcurrency static var palette: PaletteControlGroupStyle { get }
```

## Discussion



Use this style to render a multi-select or a stateless palette. The following example creates a control group that contains both type of shelves:

```swift
Menu {
    // A multi select palette
    ControlGroup {
        ForEach(ColorTags.allCases) { colorTag in
            Toggle(isOn: $selectedColorTags[colorTag]) {
                Label(colorTag.name, systemImage: "circle")
            }
            .tint(colorTag.color)
        }
    }
    .controlGroupStyle(.palette)
    .paletteSelectionEffect(.symbolVariant(.fill))

    // A momentary / stateless palette
    ControlGroup {
        ForEach(Emotes.allCases) { emote in
            Button {
                sendEmote(emote)
            } label: {
                Label(emote.name, systemImage: emote.systemImage)
            }
        }
    }
    .controlGroupStyle(.palette)
}
```

To apply this style to a control group, or to a view that contains control groups, use the [controlGroupStyle(_:)](../View/controlGroupStyle.zh-Hans.md) modifier.

## Getting built-in control group styles

- **automatic**: The default control group style.
- **compactMenu**: A control group style that presents its content as a compact menu when the user presses the control, or as a submenu when nested within a larger menu.
- **menu**: A control group style that presents its content as a menu when the user presses the control, or as a submenu when nested within a larger menu.
- **navigation**: The navigation control group style.

