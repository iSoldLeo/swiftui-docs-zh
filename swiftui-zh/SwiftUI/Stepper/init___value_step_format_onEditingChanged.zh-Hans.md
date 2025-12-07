---
来源：https://developer.apple.com/documentation/SwiftUI/Stepper/init(_:value:step:format:onEditingChanged:)
抓取时间：2025-12-01T10:34:21Z


# init(_:value:step:format:onEditingChanged:)

**Initializer**

创建带有标题键的步进器，并配置为按您提供的值和步进量递增和递减绑定，用应用的格式样式显示其值。

### 声明

```swift
nonisolated init<F>(_ titleKey: LocalizedStringKey, value: Binding<F.FormatInput>, step: F.FormatInput.Stride = 1, format: F, onEditingChanged: @escaping (Bool) -> Void = { _ in }) where F : ParseableFormatStyle, F.FormatInput : BinaryFloatingPoint, F.FormatOutput == String
```

## 参数

- **titleKey**：步进器本地化标题的关键字，描述步进器的用途。
- **value**：[Binding](../Binding.zh-Hans.md)，表示您提供的值。
- **step**：每次用户点击或轻按步进器的加号或减号按钮时，分别递增或递减`value` 的量。  默认为 `1`。
- **format**：`F`类型的格式样式，用于在用户编辑的字符串和`F.FormatInput`类型的基础值之间进行转换。如果`format` 无法执行转换，步进器将使`value` 保持不变。如果用户在无效状态下停止编辑文本，步进器会将文本更新为最后已知的有效值。
- **onEditingChanged**：编辑开始和结束时调用的闭包。例如，在 iOS 上，用户可以触摸并按住`Stepper`上的递增或递减按钮，从而在手势开始和结束时执行`onEditingChanged`闭包。

### 讨论

使用`Stepper(_:value:step:onEditingChanged:)` 创建一个带有自定义标题的步进器，该步进器按您指定的步长递增或递减绑定值，同时显示当前值。

在下面的示例中，每次用户单击或点击控件的递增或递减按钮时，步进器都会以`5`的步长递增或递减绑定值：

```swift
struct StepperView: View {
    @State private var value = 1.0
    private let step = 5.0

    var body: some View {
        Stepper("Stepping by \(step)",
            value: $value,
            step: step,
            format: .number
        )
        .padding(10)
    }
}
```



## 创建步进器

- **init(value:step:label:onEditingChanged:)**：创建步进器，配置为使用您提供的步长值将绑定值递增或递减。
- **init(value:step:format:label:onEditingChanged:)**：创建一个步进器，该步进器被配置为使用您提供的步长值递增或递减绑定值，并使用应用的格式样式显示其值。
- **init(_:value:step:onEditingChanged:)**：创建带有标题的步进器，并配置为按您提供的值和步长递增或递减绑定。


---
source: https://developer.apple.com/documentation/SwiftUI/Stepper/init(_:value:step:format:onEditingChanged:)
crawled: 2025-12-01T10:34:21Z
---

# init(_:value:step:format:onEditingChanged:)

**Initializer**

Creates a stepper with a title key and configured to increment and decrement a binding to a value and step amount you provide, displaying its value with an applied format style.

## Declaration

```swift
nonisolated init<F>(_ titleKey: LocalizedStringKey, value: Binding<F.FormatInput>, step: F.FormatInput.Stride = 1, format: F, onEditingChanged: @escaping (Bool) -> Void = { _ in }) where F : ParseableFormatStyle, F.FormatInput : BinaryFloatingPoint, F.FormatOutput == String
```

## Parameters

- **titleKey**: The key for the stepper’s localized title describing the purpose of the stepper.
- **value**: A [Binding](../Binding.zh-Hans.md) to a value that you provide.
- **step**: The amount to increment or decrement `value` each time the user clicks or taps the stepper’s plus or minus button, respectively.  Defaults to `1`.
- **format**: A format style of type `F` to use when converting between the string the user edits and the underlying value of type `F.FormatInput`. If `format` can’t perform the conversion, the stepper leaves `value` unchanged. If the user stops editing the text in an invalid state, the stepper updates the text to the last known valid value.
- **onEditingChanged**: A closure that’s called when editing begins and ends. For example, on iOS, the user may touch and hold the increment or decrement buttons on a `Stepper` which causes the execution of the `onEditingChanged` closure at the start and end of the gesture.

## Discussion

Use `Stepper(_:value:step:onEditingChanged:)` to create a stepper with a custom title that increments or decrements a binding to value by the step size you specify, while displaying the current value.

In the example below, the stepper increments or decrements the binding value by `5` each time the user clicks or taps on the control’s increment or decrement buttons, respectively:

```swift
struct StepperView: View {
    @State private var value = 1.0
    private let step = 5.0

    var body: some View {
        Stepper("Stepping by \(step)",
            value: $value,
            step: step,
            format: .number
        )
        .padding(10)
    }
}
```



## Creating a stepper

- **init(value:step:label:onEditingChanged:)**: Creates a stepper configured to increment or decrement a binding to a value using a step value you provide.
- **init(value:step:format:label:onEditingChanged:)**: Creates a stepper configured to increment or decrement a binding to a value using a step value you provide, displaying its value with an applied format style.
- **init(_:value:step:onEditingChanged:)**: Creates a stepper with a title and configured to increment and decrement a binding to a value and step amount you provide.

