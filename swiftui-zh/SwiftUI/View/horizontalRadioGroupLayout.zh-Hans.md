--- 来源：https://developer.apple.com/documentation/SwiftUI/View/horizontalRadioGroupLayout()

抓取时间：2025-12-02T17:36:04Z

---

# horizontalRadioGroupLayout()

**实例方法**

设置此视图中单选按钮组样式选择器的样式，使其水平排列。

## 声明

```swift
nonisolated func horizontalRadioGroupLayout() -> some View

```

## 说明

使用 `horizontalRadioGroupLayout()` 配置 [Picker](../Picker.zh-Hans.md) 中单选按钮的视觉布局，使其在视图中水平排列。

以下示例显示了两个配置为单选按钮组的 [Picker](../Picker.zh-Hans.md) 控件；第一个组显示默认的垂直布局；第二组展示了 `horizontalRadioGroupLayout()` 的效果，它将单选按钮水平显示。

```swift
struct HorizontalRadioGroupLayout: View {
    @State private var selected = 1
    var body: some View {
        VStack(spacing: 20) {
            Picker(selection: $selected, label: Text("Favorite Color")) {
                Text("Red").tag(1)
                Text("Green").tag(2)
                Text("Blue").tag(3)
                Text("Other").tag(4)
            }
            .pickerStyle(.radioGroup)

            Picker(selection: $selected, label: Text("Favorite Color")) {
                Text("Red").tag(1)
                Text("Green").tag(2)
                Text("Blue").tag(3)
                Text("Other").tag(4)
            }
            .pickerStyle(.radioGroup)
            .horizontalRadioGroupLayout()
        }
        .padding(20)
        .border(Color.gray)
    }
}
```

## 从一组选项中进行选择

- **Picker**：用于从一组互斥值中进行选择的控件。

- **pickerStyle(_:)**：设置此视图中选择器的样式。

- **defaultWheelPickerItemHeight(_:)**：设置默认的滚轮式选择器项的高度。

- **defaultWheelPickerItemHeight**：滚轮式选择器（例如日期选择器）中项目的默认高度。

- **paletteSelectionEffect(_:)**：指定要应用于调色板项的选择效果。

- **PaletteSelectionEffect**：要应用于调色板项的选择效果。


---
source: https://developer.apple.com/documentation/SwiftUI/View/horizontalRadioGroupLayout()
crawled: 2025-12-02T17:36:04Z
---

# horizontalRadioGroupLayout()

**Instance Method**

Sets the style for radio group style pickers within this view to be horizontally positioned with the radio buttons inside the layout.

## Declaration

```swift
nonisolated func horizontalRadioGroupLayout() -> some View

```

## Discussion

Use `horizontalRadioGroupLayout()` to configure the visual layout of radio buttons in a [Picker](../Picker.zh-Hans.md) so that the radio buttons are arranged horizontally in the view.

The example below shows two [Picker](../Picker.zh-Hans.md) controls configured as radio button groups; the first group shows the default vertical layout; the second group shows the effect of `horizontalRadioGroupLayout()` which renders the radio buttons horizontally.

```swift
struct HorizontalRadioGroupLayout: View {
    @State private var selected = 1
    var body: some View {
        VStack(spacing: 20) {
            Picker(selection: $selected, label: Text("Favorite Color")) {
                Text("Red").tag(1)
                Text("Green").tag(2)
                Text("Blue").tag(3)
                Text("Other").tag(4)
            }
            .pickerStyle(.radioGroup)

            Picker(selection: $selected, label: Text("Favorite Color")) {
                Text("Red").tag(1)
                Text("Green").tag(2)
                Text("Blue").tag(3)
                Text("Other").tag(4)
            }
            .pickerStyle(.radioGroup)
            .horizontalRadioGroupLayout()
        }
        .padding(20)
        .border(Color.gray)
    }
}
```



## Choosing from a set of options

- **Picker**: A control for selecting from a set of mutually exclusive values.
- **pickerStyle(_:)**: Sets the style for pickers within this view.
- **defaultWheelPickerItemHeight(_:)**: Sets the default wheel-style picker item height.
- **defaultWheelPickerItemHeight**: The default height of an item in a wheel-style picker, such as a date picker.
- **paletteSelectionEffect(_:)**: Specifies the selection effect to apply to a palette item.
- **PaletteSelectionEffect**: The selection effect to apply to a palette item.

