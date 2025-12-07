---
来源：https://developer.apple.com/documentation/SwiftUI/Stepper/init(value:in:step:format:label:onEditingChanged:)
抓取时间：2025-12-01T10:34:23Z
---

# init(value:in:step:format:label:onEditingChanged:)

**Initializer**

创建步进器，配置为使用步进值在您提供的值范围内递增或递减绑定值，并使用应用的格式样式显示其值。

### 声明

```swift
nonisolated init<F>(value: Binding<F.FormatInput>, in bounds: ClosedRange<F.FormatInput>, step: F.FormatInput.Stride = 1, format: F, @ViewBuilder label: () -> Label, onEditingChanged: @escaping (Bool) -> Void = { _ in }) where F : ParseableFormatStyle, F.FormatInput : BinaryFloatingPoint, F.FormatOutput == String
```

## 参数

- **value**：[Binding](../Binding.zh-Hans.md)到您提供的值。
- **bounds**：描述步进器允许的上下限的封闭范围。
- **step**：当用户点击或轻按步进器的递增或递减按钮时，步进器分别递增或递减的量。
- **format**：`F`类型的格式样式，用于在用户编辑的字符串和`F.FormatInput`类型的基础值之间进行转换。如果`format` 无法执行转换，步进器将使`value` 保持不变。如果用户在无效状态下停止编辑文本，步进器会将文本更新为最后已知的有效值。
- **label**：描述该步进器用途的视图。
- **onEditingChanged**：编辑开始和结束时调用的闭包。例如，在 iOS 上，用户可以触摸并按住步进器上的递增或递减按钮，从而在手势开始和结束时执行`onEditingChanged` 闭包。

## 讨论

使用此初始化程序创建一个步进器，在给定的范围内按照您提供的步长递增或递减绑定值。通过设置界限，可以确保数值永远不会低于或高于最低或最高值。

下面的示例显示了一个步进器，该步进器显示了以 `step` 步长递增或递减数值的效果，其界限由 `range` 定义：

```swift
struct StepperView: View {
    @State private var value = 0.0
    let step = 5.0
    let range = 1.0...50.0

    var body: some View {
        Stepper(value: $value,
                in: range,
                step: step,
                format: .number) {
            Text("Current: \(value) in \(range.description) " +
                 "stepping by \(step)")
        }
            .padding(10)
    }
}
```



## 在一定范围内创建步进器

- **init(value:in:step:label:onEditingChanged:)**：创建步进器，配置为使用步进值并在您提供的值范围内递增或递减绑定值。
- **init(_:value:in:step:onEditingChanged:)**：创建一个步进实例，在您提供的封闭范围内，按步长递增或递减绑定值。
- **init(_:value:in:step:format:onEditingChanged:)**：创建一个步进器实例，在您提供的封闭范围内按步长递增和递减绑定值，并以应用的格式样式显示其值。


---
source: https://developer.apple.com/documentation/SwiftUI/Stepper/init(value:in:step:format:label:onEditingChanged:)
crawled: 2025-12-01T10:34:23Z
---

# init(value:in:step:format:label:onEditingChanged:)

**Initializer**

Creates a stepper configured to increment or decrement a binding to a value using a step value and within a range of values you provide, displaying its value with an applied format style.

## Declaration

```swift
nonisolated init<F>(value: Binding<F.FormatInput>, in bounds: ClosedRange<F.FormatInput>, step: F.FormatInput.Stride = 1, format: F, @ViewBuilder label: () -> Label, onEditingChanged: @escaping (Bool) -> Void = { _ in }) where F : ParseableFormatStyle, F.FormatInput : BinaryFloatingPoint, F.FormatOutput == String
```

## Parameters

- **value**: A [Binding](../Binding.zh-Hans.md) to a value that you provide.
- **bounds**: A closed range that describes the upper and lower bounds permitted by the stepper.
- **step**: The amount to increment or decrement the stepper when the user clicks or taps the stepper’s increment or decrement buttons, respectively.
- **format**: A format style of type `F` to use when converting between the string the user edits and the underlying value of type `F.FormatInput`. If `format` can’t perform the conversion, the stepper leaves `value` unchanged. If the user stops editing the text in an invalid state, the stepper updates the text to the last known valid value.
- **label**: A view describing the purpose of this stepper.
- **onEditingChanged**: A closure that’s called when editing begins and ends. For example, on iOS, the user may touch and hold the increment or decrement buttons on a stepper which causes the execution of the `onEditingChanged` closure at the start and end of the gesture.

## Discussion

Use this initializer to create a stepper that increments or decrements a binding to value by the step size you provide within the given bounds. By setting the bounds, you ensure that the value never goes below or above the lowest or highest value, respectively.

The example below shows a stepper that displays the effect of incrementing or decrementing a value with the step size of `step` with the bounds defined by `range`:

```swift
struct StepperView: View {
    @State private var value = 0.0
    let step = 5.0
    let range = 1.0...50.0

    var body: some View {
        Stepper(value: $value,
                in: range,
                step: step,
                format: .number) {
            Text("Current: \(value) in \(range.description) " +
                 "stepping by \(step)")
        }
            .padding(10)
    }
}
```



## Creating a stepper over a range

- **init(value:in:step:label:onEditingChanged:)**: Creates a stepper configured to increment or decrement a binding to a value using a step value and within a range of values you provide.
- **init(_:value:in:step:onEditingChanged:)**: Creates a stepper instance that increments and decrements a binding to a value, by a step size and within a closed range that you provide.
- **init(_:value:in:step:format:onEditingChanged:)**: Creates a stepper instance that increments and decrements a binding to a value, by a step size and within a closed range that you provide, displaying its value with an applied format style.

