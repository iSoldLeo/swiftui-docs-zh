--- 来源：https://developer.apple.com/documentation/SwiftUI/View/defaultWheelPickerItemHeight(_:)

抓取时间：2025-11-30T21:21:09Z

---

# defaultWheelPickerItemHeight(_:)

**实例方法**

设置默认的滚轮式选择器项高度。

## 声明

```swift
nonisolated func defaultWheelPickerItemHeight(_ height: CGFloat) -> some View

```

## 参数

- **height**：选择器项的高度。

## 说明

当需要更改选择器控件中的默认项高度时，请使用 `defaultWheelPickerItemHeight(_:)`。在本例中，视图将选择器元素的默认高度设置为 30 磅。

```swift
struct DefaultWheelPickerItemHeight: View {
    @State private var selected = 1
    var body: some View {
        VStack(spacing: 20) {
            Picker(selection: $selected, label: Text("Favorite Color")) {
                Text("Red").tag(1)
                Text("Green").tag(2)
                Text("Blue").tag(3)
                Text("Other").tag(4)
            }
        }
        .defaultWheelPickerItemHeight(30)
    }
}
```

## 从一组选项中进行选择

- **Picker**：用于从一组互斥值中进行选择的控件。

- **pickerStyle(_:)**：设置此视图中选择器的样式。

- **horizontalRadioGroupLayout()**：设置此视图中单选按钮组样式选择器的样式，使其水平排列，单选按钮位于布局内。

- **defaultWheelPickerItemHeight**：轮状选择器（例如日期选择器）中项目的默认高度。

- **paletteSelectionEffect(_:)**：指定要应用于调色板项目的选择效果。

- **PaletteSelectionEffect**：要应用于调色板项目的选择效果。


---
source: https://developer.apple.com/documentation/SwiftUI/View/defaultWheelPickerItemHeight(_:)
crawled: 2025-11-30T21:21:09Z
---

# defaultWheelPickerItemHeight(_:)

**Instance Method**

Sets the default wheel-style picker item height.

## Declaration

```swift
nonisolated func defaultWheelPickerItemHeight(_ height: CGFloat) -> some View

```

## Parameters

- **height**: The height for the picker items.

## Discussion

Use `defaultWheelPickerItemHeight(_:)` when you need to change the default item height in a picker control. In this example, the view sets the default height for picker elements to 30 points.

```swift
struct DefaultWheelPickerItemHeight: View {
    @State private var selected = 1
    var body: some View {
        VStack(spacing: 20) {
            Picker(selection: $selected, label: Text("Favorite Color")) {
                Text("Red").tag(1)
                Text("Green").tag(2)
                Text("Blue").tag(3)
                Text("Other").tag(4)
            }
        }
        .defaultWheelPickerItemHeight(30)
    }
}
```



## Choosing from a set of options

- **Picker**: A control for selecting from a set of mutually exclusive values.
- **pickerStyle(_:)**: Sets the style for pickers within this view.
- **horizontalRadioGroupLayout()**: Sets the style for radio group style pickers within this view to be horizontally positioned with the radio buttons inside the layout.
- **defaultWheelPickerItemHeight**: The default height of an item in a wheel-style picker, such as a date picker.
- **paletteSelectionEffect(_:)**: Specifies the selection effect to apply to a palette item.
- **PaletteSelectionEffect**: The selection effect to apply to a palette item.

