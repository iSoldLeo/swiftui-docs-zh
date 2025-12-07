---
来源：https://developer.apple.com/documentation/SwiftUI/Stepper/init(value:step:label:onEditingChanged:)
抓取时间：2025-12-01T10:34:19Z


# init(value:step:label:onEditingChanged:)

**Initializer**

创建步进器，配置为使用您提供的步进值递增或递减绑定值。

### 声明

```swift
nonisolated init<V>(value: Binding<V>, step: V.Stride = 1, @ViewBuilder label: () -> Label, onEditingChanged: @escaping (Bool) -> Void = { _ in }) where V : Strideable
```

## 参数

- **value**：[Binding](../Binding.zh-Hans.md)到您提供的值。
- **step**：每次用户点击或敲击步进器的递增或递减按钮时，递增或递减`value` 的量。默认为 `1`。
- **label**：描述该步进器用途的视图。
- **onEditingChanged**：编辑开始和结束时调用的闭包。例如，在 iOS 上，用户可以触摸并按住步进器上的递增或递减按钮，从而在手势开始和结束时执行`onEditingChanged` 闭包。

## 讨论

使用该初始化程序创建一个步进器，每次用户点击或敲击步进器的递增或递减按钮时，该步进器都会以特定的量递增或递减一个绑定值。

在下面的示例中，每次点击或敲击控件的递增或递减按钮时，步进器都会递增或递减`value`，递增或递减的`step`值为 5：

```swift
struct StepperView: View {
    @State private var value = 1
    let step = 5
    var body: some View {
        Stepper(value: $value,
                step: step) {
            Text("Current value: \(value), step: \(step)")
        }
            .padding(10)
    }
}
```



## 创建步进器

- **init(value:step:format:label:onEditingChanged:)**：创建步进器，配置为使用您提供的步进值递增或递减绑定值，并使用应用的格式样式显示其值。
- **init(_:value:step:onEditingChanged:)**：创建带标题的步进器，并配置为按您提供的值和步进量递增和递减绑定。
- **init(_:value:step:format:onEditingChanged:)**：创建带有标题键的步进器，并配置为按您提供的值和步长递增和递减绑定，用应用的格式样式显示其值。


---
source: https://developer.apple.com/documentation/SwiftUI/Stepper/init(value:step:label:onEditingChanged:)
crawled: 2025-12-01T10:34:19Z
---

# init(value:step:label:onEditingChanged:)

**Initializer**

Creates a stepper configured to increment or decrement a binding to a value using a step value you provide.

## Declaration

```swift
nonisolated init<V>(value: Binding<V>, step: V.Stride = 1, @ViewBuilder label: () -> Label, onEditingChanged: @escaping (Bool) -> Void = { _ in }) where V : Strideable
```

## Parameters

- **value**: The [Binding](../Binding.zh-Hans.md) to a value that you provide.
- **step**: The amount to increment or decrement `value` each time the user clicks or taps the stepper’s increment or decrement buttons. Defaults to `1`.
- **label**: A view describing the purpose of this stepper.
- **onEditingChanged**: A closure that’s called when editing begins and ends. For example, on iOS, the user may touch and hold the increment or decrement buttons on a stepper which causes the execution of the `onEditingChanged` closure at the start and end of the gesture.

## Discussion

Use this initializer to create a stepper that increments or decrements a bound value by a specific amount each time the user clicks or taps the stepper’s increment or decrement buttons.

In the example below, a stepper increments or decrements `value` by the `step` value of 5 at each click or tap of the control’s increment or decrement button:

```swift
struct StepperView: View {
    @State private var value = 1
    let step = 5
    var body: some View {
        Stepper(value: $value,
                step: step) {
            Text("Current value: \(value), step: \(step)")
        }
            .padding(10)
    }
}
```



## Creating a stepper

- **init(value:step:format:label:onEditingChanged:)**: Creates a stepper configured to increment or decrement a binding to a value using a step value you provide, displaying its value with an applied format style.
- **init(_:value:step:onEditingChanged:)**: Creates a stepper with a title and configured to increment and decrement a binding to a value and step amount you provide.
- **init(_:value:step:format:onEditingChanged:)**: Creates a stepper with a title key and configured to increment and decrement a binding to a value and step amount you provide, displaying its value with an applied format style.

