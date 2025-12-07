---
来源：https://developer.apple.com/documentation/SwiftUI/Stepper/init(_:value:step:onEditingChanged:)
抓取时间：2025-12-01T10:34:20Z


# init(_:value:step:onEditingChanged:)

**Initializer**

创建带有标题的步进器，并配置为按您提供的值和步长递增或递减绑定。

### 声明

```swift
nonisolated init<S, V>(_ title: S, value: Binding<V>, step: V.Stride = 1, onEditingChanged: @escaping (Bool) -> Void = { _ in }) where S : StringProtocol, V : Strideable
```

## 参数

- **title**：描述步进器用途的字符串。
- **value**：[Binding](../Binding.zh-Hans.md)到您提供的值。
- **step**：每次用户点击或轻按步进器的递增或递减按钮时，分别递增或递减`value` 的量。默认为 `1`。
- **onEditingChanged**：编辑开始和结束时调用的闭包。例如，在 iOS 上，用户可以触摸并按住`Stepper` 上的递增或递减按钮，从而在手势开始和结束时执行`onEditingChanged` 闭包。

### 讨论

使用`Stepper(_:value:step:onEditingChanged:)` 创建一个带有自定义标题的步进器，该步进器按您指定的步长递增或递减绑定值。

在下面的示例中，每次用户点击或轻按控件的递增或递减按钮时，步进器都会递增或递减绑定值`5`：

```swift
struct StepperView: View {
    @State private var value = 1
    let step = 5
    let title: String

    var body: some View {
        Stepper(title, value: $value, step: step)
            .padding(10)
    }
}
```



## 创建步进器

- **init(value:step:label:onEditingChanged:)**：创建步进器，配置为使用您提供的步长值将绑定值递增或递减。
- **init(value:step:format:label:onEditingChanged:)**：创建一个步进器，该步进器被配置为使用您提供的步长值递增或递减绑定值，并使用应用的格式样式显示其值。
- **init(_:value:step:format:onEditingChanged:)**：创建带有标题键的步进器，该步进器被配置为按您提供的值和步长递增或递减绑定，并以应用的格式样式显示其值。


---
source: https://developer.apple.com/documentation/SwiftUI/Stepper/init(_:value:step:onEditingChanged:)
crawled: 2025-12-01T10:34:20Z
---

# init(_:value:step:onEditingChanged:)

**Initializer**

Creates a stepper with a title and configured to increment and decrement a binding to a value and step amount you provide.

## Declaration

```swift
nonisolated init<S, V>(_ title: S, value: Binding<V>, step: V.Stride = 1, onEditingChanged: @escaping (Bool) -> Void = { _ in }) where S : StringProtocol, V : Strideable
```

## Parameters

- **title**: A string describing the purpose of the stepper.
- **value**: The [Binding](../Binding.zh-Hans.md) to a value that you provide.
- **step**: The amount to increment or decrement `value` each time the user clicks or taps the stepper’s increment or decrement button, respectively. Defaults to `1`.
- **onEditingChanged**: A closure that’s called when editing begins and ends. For example, on iOS, the user may touch and hold the increment or decrement buttons on a `Stepper` which causes the execution of the `onEditingChanged` closure at the start and end of the gesture.

## Discussion

Use `Stepper(_:value:step:onEditingChanged:)` to create a stepper with a custom title that increments or decrements a binding to value by the step size you specify.

In the example below, the stepper increments or decrements the binding value by `5` each time one of the user clicks or taps the control’s increment or decrement buttons:

```swift
struct StepperView: View {
    @State private var value = 1
    let step = 5
    let title: String

    var body: some View {
        Stepper(title, value: $value, step: step)
            .padding(10)
    }
}
```



## Creating a stepper

- **init(value:step:label:onEditingChanged:)**: Creates a stepper configured to increment or decrement a binding to a value using a step value you provide.
- **init(value:step:format:label:onEditingChanged:)**: Creates a stepper configured to increment or decrement a binding to a value using a step value you provide, displaying its value with an applied format style.
- **init(_:value:step:format:onEditingChanged:)**: Creates a stepper with a title key and configured to increment and decrement a binding to a value and step amount you provide, displaying its value with an applied format style.

