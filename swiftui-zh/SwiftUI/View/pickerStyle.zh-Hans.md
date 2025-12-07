--- 来源：https://developer.apple.com/documentation/SwiftUI/View/pickerStyle(_:)

抓取时间：2025-12-02T17:33:04Z

---

# pickerStyle(_:)

**实例方法**

设置此视图中选择器的样式。

## 声明

```swift
nonisolated func pickerStyle<S>(_ style: S) -> some View where S : PickerStyle

```

## 从一组选项中进行选择

- **Picker**：用于从一组互斥值中进行选择的控件。

- **horizontalRadioGroupLayout()**：设置此视图中单选按钮组样式选择器的样式，使其水平排列，单选按钮位于布局内。

- **defaultWheelPickerItemHeight(_:)**：设置默认的滚轮式选择器项的高度。

- **defaultWheelPickerItemHeight**：轮盘式选择器（例如日期选择器）中项目的默认高度。

- **paletteSelectionEffect(_:)**：指定应用于调色板项目的选择效果。

- **PaletteSelectionEffect**：应用于调色板项目的选择效果。


---
source: https://developer.apple.com/documentation/SwiftUI/View/pickerStyle(_:)
crawled: 2025-12-02T17:33:04Z
---

# pickerStyle(_:)

**Instance Method**

Sets the style for pickers within this view.

## Declaration

```swift
nonisolated func pickerStyle<S>(_ style: S) -> some View where S : PickerStyle

```

## Choosing from a set of options

- **Picker**: A control for selecting from a set of mutually exclusive values.
- **horizontalRadioGroupLayout()**: Sets the style for radio group style pickers within this view to be horizontally positioned with the radio buttons inside the layout.
- **defaultWheelPickerItemHeight(_:)**: Sets the default wheel-style picker item height.
- **defaultWheelPickerItemHeight**: The default height of an item in a wheel-style picker, such as a date picker.
- **paletteSelectionEffect(_:)**: Specifies the selection effect to apply to a palette item.
- **PaletteSelectionEffect**: The selection effect to apply to a palette item.

