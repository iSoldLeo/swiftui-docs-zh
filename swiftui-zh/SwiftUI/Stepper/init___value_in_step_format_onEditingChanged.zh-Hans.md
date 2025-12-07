---
来源：https://developer.apple.com/documentation/SwiftUI/Stepper/init(_:value:in:step:format:onEditingChanged:)
抓取时间：2025-12-01T10:34:24Z


# init(_:value:in:step:format:onEditingChanged:)

**Initializer**

创建一个步进器实例，在您提供的封闭范围内按步进大小递增或递减绑定值，并以应用的格式样式显示其值。

### 声明

```swift
nonisolated init<F>(_ titleKey: LocalizedStringKey, value: Binding<F.FormatInput>, in bounds: ClosedRange<F.FormatInput>, step: F.FormatInput.Stride = 1, format: F, onEditingChanged: @escaping (Bool) -> Void = { _ in }) where F : ParseableFormatStyle, F.FormatInput : BinaryFloatingPoint, F.FormatOutput == String
```

## 参数

- **titleKey**：步进器本地化标题的关键字，描述步进器的用途。
- **value**：[Binding](../Binding.zh-Hans.md)，表示您提供的值。
- **bounds**：描述步进器允许的上下限的封闭范围。
- **step**：每次用户点击或轻按步进器的递增或递减按钮时，分别递增或递减`value` 的量。默认为 `1`。
- **format**：`F`类型的格式样式，用于在用户编辑的字符串和`F.FormatInput`类型的基础值之间进行转换。如果`format` 无法执行转换，步进器将使`value` 保持不变。如果用户在无效状态下停止编辑文本，步进器会将文本更新为最后已知的有效值。
- **onEditingChanged**：编辑开始和结束时调用的闭包。例如，在 iOS 上，用户可以触摸并按住`Stepper`上的递增或递减按钮，从而在手势开始和结束时执行`onEditingChanged`闭包。

## 讨论

使用`Stepper(_:value:in:step:format:onEditingChanged:)` 创建一个步进器，在特定数值范围内以特定步长递增或递减数值，同时显示当前数值。在下面的示例中，用户每次单击或点击步进器的递增或递减按钮时，步进器都会将`1...50`范围内的绑定值递增或递减`5`：

```swift
struct StepperView: View {
    @State private var value = 0
    private let step = 5.0
    private let range = 1.0...50.0

    var body: some View {
        Stepper("Stepping by \(step) in \(range.description)",
            value: $value,
            in: range,
            step: step,
            format: .number
        )
        .padding()
    }
}
```

## 在一定范围内创建步进器

- **init(value:in:step:label:onEditingChanged:)**：创建步进器，配置为使用步进值并在您提供的值范围内递增或递减绑定值。
- **init(value:in:step:format:label:onEditingChanged:)**：创建步进器，配置为使用步进值在您提供的值范围内递增或递减绑定值，并使用应用的格式样式显示其值。
- **init(_:value:in:step:onEditingChanged:)**：创建一个步进实例，在您提供的封闭范围内按步进大小递增和递减绑定值。


---
source: https://developer.apple.com/documentation/SwiftUI/Stepper/init(_:value:in:step:format:onEditingChanged:)
crawled: 2025-12-01T10:34:24Z
---

# init(_:value:in:step:format:onEditingChanged:)

**Initializer**

Creates a stepper instance that increments and decrements a binding to a value, by a step size and within a closed range that you provide, displaying its value with an applied format style.

## Declaration

```swift
nonisolated init<F>(_ titleKey: LocalizedStringKey, value: Binding<F.FormatInput>, in bounds: ClosedRange<F.FormatInput>, step: F.FormatInput.Stride = 1, format: F, onEditingChanged: @escaping (Bool) -> Void = { _ in }) where F : ParseableFormatStyle, F.FormatInput : BinaryFloatingPoint, F.FormatOutput == String
```

## Parameters

- **titleKey**: The key for the stepper’s localized title describing the purpose of the stepper.
- **value**: A [Binding](../Binding.zh-Hans.md) to a value that your provide.
- **bounds**: A closed range that describes the upper and lower bounds permitted by the stepper.
- **step**: The amount to increment or decrement `value` each time the user clicks or taps the stepper’s increment or decrement button, respectively. Defaults to `1`.
- **format**: A format style of type `F` to use when converting between the string the user edits and the underlying value of type `F.FormatInput`. If `format` can’t perform the conversion, the stepper leaves `value` unchanged. If the user stops editing the text in an invalid state, the stepper updates the text to the last known valid value.
- **onEditingChanged**: A closure that’s called when editing begins and ends. For example, on iOS, the user may touch and hold the increment or decrement buttons on a `Stepper` which causes the execution of the `onEditingChanged` closure at the start and end of the gesture.

## Discussion

Use `Stepper(_:value:in:step:format:onEditingChanged:)` to create a stepper that increments or decrements a value within a specific range of values by a specific step size, while displaying the current value. In the example below, a stepper increments or decrements a binding to value over a range of `1...50` by `5` each time the user clicks or taps the stepper’s increment or decrement buttons:

```swift
struct StepperView: View {
    @State private var value = 0
    private let step = 5.0
    private let range = 1.0...50.0

    var body: some View {
        Stepper("Stepping by \(step) in \(range.description)",
            value: $value,
            in: range,
            step: step,
            format: .number
        )
        .padding()
    }
}
```

## Creating a stepper over a range

- **init(value:in:step:label:onEditingChanged:)**: Creates a stepper configured to increment or decrement a binding to a value using a step value and within a range of values you provide.
- **init(value:in:step:format:label:onEditingChanged:)**: Creates a stepper configured to increment or decrement a binding to a value using a step value and within a range of values you provide, displaying its value with an applied format style.
- **init(_:value:in:step:onEditingChanged:)**: Creates a stepper instance that increments and decrements a binding to a value, by a step size and within a closed range that you provide.

