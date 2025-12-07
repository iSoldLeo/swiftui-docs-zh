--- 来源：https://developer.apple.com/documentation/SwiftUI/View/paletteSelectionEffect(_:)

抓取时间：2025-11-30T21:21:11Z

---

# paletteSelectionEffect(_:)

**实例方法**

指定要应用于调色板项的选择效果。

## 声明

```swift
nonisolated func paletteSelectionEffect(_ effect: PaletteSelectionEffect) -> some View

```

## 参数

- **effect**：选中调色板项时要应用的效果类型。

## 说明

[automatic](../PaletteSelectionEffect/automatic.zh-Hans.md)：选中时应用系统的默认外观。使用未着色的 SF Symbols 或模板图像时，当前着色颜色将应用于所选项的图像。如果提供的 SF Symbols 具有自定义着色，则会在所选项周围绘制描边。

如果您希望使用特定的图像（或 SF 符号）来指示选中状态，请使用 [custom](../PaletteSelectionEffect/custom.zh-Hans.md) 来放弃系统的默认选择外观，从而仅使用提供的图像来指示选中状态。

以下示例创建了一个禁用系统选择行为的调色板选择器：

```swift
Menu {
    Picker("Palettes", selection: $selection) {
        ForEach(palettes) { palette in
            Label(palette.title, image: selection == palette ?
                  "selected-palette" : "palette")
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

如果您更倾向于使用特定的 SF 符号变体，请使用 [symbolVariant(_:)](../PaletteSelectionEffect/symbolVariant.zh-Hans.md)。

```swift
Menu {
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
}
```

## 从一组选项中进行选择

- **Picker**：用于从一组互斥值中进行选择的控件。

- **pickerStyle(_:)**：设置此视图中选择器的样式。

- **horizontalRadioGroupLayout()**：设置此视图中单选按钮组样式选择器的样式，使其水平排列，单选按钮位于布局内部。

- **defaultWheelPickerItemHeight(_:)**：设置默认的轮盘式选择器项目高度。

- **defaultWheelPickerItemHeight**：轮盘式选择器（例如日期选择器）中项目的默认高度。

- **PaletteSelectionEffect**：应用于调色板项目的选择效果。


---
source: https://developer.apple.com/documentation/SwiftUI/View/paletteSelectionEffect(_:)
crawled: 2025-11-30T21:21:11Z
---

# paletteSelectionEffect(_:)

**Instance Method**

Specifies the selection effect to apply to a palette item.

## Declaration

```swift
nonisolated func paletteSelectionEffect(_ effect: PaletteSelectionEffect) -> some View

```

## Parameters

- **effect**: The type of effect to apply when a palette item is selected.

## Discussion

[automatic](../PaletteSelectionEffect/automatic.zh-Hans.md) applies the system’s default appearance when selected. When using un-tinted SF Symbols or template images, the current tint color is applied to the selected items’ image. If the provided SF Symbols have custom tints, a stroke is drawn around selected items.

If you wish to provide a specific image (or SF Symbol) to indicate selection, use [custom](../PaletteSelectionEffect/custom.zh-Hans.md) to forgo the system’s default selection appearance allowing the provided image to solely indicate selection instead.

The following example creates a palette picker that disables the system selection behavior:

```swift
Menu {
    Picker("Palettes", selection: $selection) {
        ForEach(palettes) { palette in
            Label(palette.title, image: selection == palette ?
                  "selected-palette" : "palette")
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

If a specific SF Symbol variant is preferable instead, use [symbolVariant(_:)](../PaletteSelectionEffect/symbolVariant.zh-Hans.md).

```swift
Menu {
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
}
```

## Choosing from a set of options

- **Picker**: A control for selecting from a set of mutually exclusive values.
- **pickerStyle(_:)**: Sets the style for pickers within this view.
- **horizontalRadioGroupLayout()**: Sets the style for radio group style pickers within this view to be horizontally positioned with the radio buttons inside the layout.
- **defaultWheelPickerItemHeight(_:)**: Sets the default wheel-style picker item height.
- **defaultWheelPickerItemHeight**: The default height of an item in a wheel-style picker, such as a date picker.
- **PaletteSelectionEffect**: The selection effect to apply to a palette item.

