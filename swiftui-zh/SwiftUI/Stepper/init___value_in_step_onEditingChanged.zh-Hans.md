---
来源：https://developer.apple.com/documentation/SwiftUI/Stepper/init(_:value:in:step:onEditingChanged:)
抓取时间： 2025-12-01T10:34:24Z


# init(_:value:in:step:onEditingChanged:)

**Initializer**

创建步进器实例，在您提供的封闭范围内，按步进大小递增或递减绑定值。

### 声明

```swift
nonisolated init<S, V>(_ title: S, value: Binding<V>, in bounds: ClosedRange<V>, step: V.Stride = 1, onEditingChanged: @escaping (Bool) -> Void = { _ in }) where S : StringProtocol, V : Strideable
```

## 参数

- **title**：描述步进器用途的字符串。
- **value**：[Binding](../Binding.zh-Hans.md)，表示您提供的值。
- **bounds**：描述步进器允许的上下限的封闭范围。
- **step**：每次用户点击或轻按步进器的递增或递减按钮时，分别递增或递减`value` 的量。默认为 `1`。
- **onEditingChanged**：编辑开始和结束时调用的闭包。例如，在 iOS 上，用户可以触摸并按住`Stepper`上的递增或递减按钮，从而在手势开始和结束时执行`onEditingChanged`闭包。

## 讨论

使用`Stepper(_:value:in:step:onEditingChanged:)` 创建一个步进器，在特定数值范围内以特定步长递增或递减数值。在下面的示例中，用户每次单击或点击步进器的递增或递减按钮时，步进器都会在`1...50` 的范围内将`5` 的绑定值递增或递减：

```swift
struct StepperView: View {
    @State private var value = 0
    let step = 5
    let range = 1...50

    var body: some View {
        Stepper("Current: \(value) in \(range.description) stepping by \(step)",
                value: $value,
                in: range,
                step: step)
            .padding(10)
    }
}
```



## 在一定范围内创建步进器

- **init(value:in:step:label:onEditingChanged:)**：创建步进器，配置为使用步进值并在您提供的值范围内递增或递减绑定值。
- **init(value:in:step:format:label:onEditingChanged:)**：创建步进器，配置为使用步进值在您提供的值范围内递增或递减绑定值，并使用应用的格式样式显示其值。
- **init(_:value:in:step:format:onEditingChanged:)**：创建一个步进实例，在您提供的封闭范围内，按步进值大小递增和递减绑定值，并以应用的格式样式显示其值。


---
source: https://developer.apple.com/documentation/SwiftUI/Stepper/init(_:value:in:step:onEditingChanged:)
crawled: 2025-12-01T10:34:24Z
---

# init(_:value:in:step:onEditingChanged:)

**Initializer**

Creates a stepper instance that increments and decrements a binding to a value, by a step size and within a closed range that you provide.

## Declaration

```swift
nonisolated init<S, V>(_ title: S, value: Binding<V>, in bounds: ClosedRange<V>, step: V.Stride = 1, onEditingChanged: @escaping (Bool) -> Void = { _ in }) where S : StringProtocol, V : Strideable
```

## Parameters

- **title**: A string describing the purpose of the stepper.
- **value**: A [Binding](../Binding.zh-Hans.md) to a value that your provide.
- **bounds**: A closed range that describes the upper and lower bounds permitted by the stepper.
- **step**: The amount to increment or decrement `value` each time the user clicks or taps the stepper’s increment or decrement button, respectively. Defaults to `1`.
- **onEditingChanged**: A closure that’s called when editing begins and ends. For example, on iOS, the user may touch and hold the increment or decrement buttons on a `Stepper` which causes the execution of the `onEditingChanged` closure at the start and end of the gesture.

## Discussion

Use `Stepper(_:value:in:step:onEditingChanged:)` to create a stepper that increments or decrements a value within a specific range of values by a specific step size. In the example below, a stepper increments or decrements a binding to value over a range of `1...50` by `5` each time the user clicks or taps the stepper’s increment or decrement buttons:

```swift
struct StepperView: View {
    @State private var value = 0
    let step = 5
    let range = 1...50

    var body: some View {
        Stepper("Current: \(value) in \(range.description) stepping by \(step)",
                value: $value,
                in: range,
                step: step)
            .padding(10)
    }
}
```



## Creating a stepper over a range

- **init(value:in:step:label:onEditingChanged:)**: Creates a stepper configured to increment or decrement a binding to a value using a step value and within a range of values you provide.
- **init(value:in:step:format:label:onEditingChanged:)**: Creates a stepper configured to increment or decrement a binding to a value using a step value and within a range of values you provide, displaying its value with an applied format style.
- **init(_:value:in:step:format:onEditingChanged:)**: Creates a stepper instance that increments and decrements a binding to a value, by a step size and within a closed range that you provide, displaying its value with an applied format style.

