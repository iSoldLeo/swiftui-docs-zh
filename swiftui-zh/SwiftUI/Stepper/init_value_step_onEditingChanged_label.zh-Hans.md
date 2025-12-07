---
来源：https://developer.apple.com/documentation/SwiftUI/Stepper/init(value:step:onEditingChanged:label:)
抓取时间：2025-12-01T10:34:27Z


# init(value:step:onEditingChanged:label:)

**Initializer**

创建步进器，配置为使用您提供的步进值递增或递减绑定值。

### 声明

```swift
nonisolated init<V>(value: Binding<V>, step: V.Stride = 1, onEditingChanged: @escaping (Bool) -> Void = { _ in }, @ViewBuilder label: () -> Label) where V : Strideable
```

## 参数

- **value**：[Binding](../Binding.zh-Hans.md)到您提供的值。
- **step**：每次用户点击或敲击步进器的递增或递减按钮时，递增或递减`value` 的量。默认为 `1`。
- **onEditingChanged**：编辑开始和结束时调用的闭包。例如，在 iOS 上，用户可以触摸并按住步进器上的递增或递减按钮，从而在手势开始和结束时执行`onEditingChanged` 闭包。
- **label**：描述该步进器用途的视图。

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



## 过时的初始化程序

- **init(value:in:step:onEditingChanged:label:)**：创建步进器，配置为使用步进值在您提供的值范围内递增或递减绑定值。
- **init(onIncrement:onDecrement:onEditingChanged:label:)**：创建步进器实例，在用户递增或递减步进器时执行您提供的闭合。


---
source: https://developer.apple.com/documentation/SwiftUI/Stepper/init(value:step:onEditingChanged:label:)
crawled: 2025-12-01T10:34:27Z
---

# init(value:step:onEditingChanged:label:)

**Initializer**

Creates a stepper configured to increment or decrement a binding to a value using a step value you provide.

## Declaration

```swift
nonisolated init<V>(value: Binding<V>, step: V.Stride = 1, onEditingChanged: @escaping (Bool) -> Void = { _ in }, @ViewBuilder label: () -> Label) where V : Strideable
```

## Parameters

- **value**: The [Binding](../Binding.zh-Hans.md) to a value that you provide.
- **step**: The amount to increment or decrement `value` each time the user clicks or taps the stepper’s increment or decrement buttons. Defaults to `1`.
- **onEditingChanged**: A closure that’s called when editing begins and ends. For example, on iOS, the user may touch and hold the increment or decrement buttons on a stepper which causes the execution of the `onEditingChanged` closure at the start and end of the gesture.
- **label**: A view describing the purpose of this stepper.

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



## Deprecated initializers

- **init(value:in:step:onEditingChanged:label:)**: Creates a stepper configured to increment or decrement a binding to a value using a step value and within a range of values you provide.
- **init(onIncrement:onDecrement:onEditingChanged:label:)**: Creates a stepper instance that performs the closures you provide when the user increments or decrements the stepper.

