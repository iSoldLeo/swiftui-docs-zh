---
来源：https://developer.apple.com/documentation/SwiftUI/Stepper/init(onIncrement:onDecrement:onEditingChanged:label:)
抓取时间： 2025-12-01T10:34:28Z


# init(onIncrement:onDecrement:onEditingChanged:label:)

**Initializer**

创建步进器实例，当用户递增或递减步进器时执行您提供的闭包。

## 声明

```swift
nonisolated init(onIncrement: (() -> Void)?, onDecrement: (() -> Void)?, onEditingChanged: @escaping (Bool) -> Void = { _ in }, @ViewBuilder label: () -> Label)
```

## 参数

- **onIncrement**：当用户点击或轻按控件的加号按钮时要执行的闭包。
- **onDecrement**：当用户点击或轻按控件的减号按钮时要执行的闭包。
- **onEditingChanged**：编辑开始和结束时调用的闭包。例如，在 iOS 上，用户可以触摸并按住`Stepper`上的递增或递减按钮，从而在手势开始和结束时执行`onEditingChanged`闭包。
- **label**：描述该步进器用途的视图。

## 讨论

使用该初始化程序可创建一个带有自定义标题的控件，当用户点击或轻按步进器的递增或递减按钮时，该控件将执行您提供的闭包。

下面的示例使用了一个数组来保存一些[Color](../Color.zh-Hans.md) 值、一个本地状态变量`value` 来设置控件的背景颜色和标题标签。当用户点击或轻按步进器的递增或递减按钮时，SwiftUI 会执行相关的闭包，更新`value`，并封装`value`，以防止溢出。然后，SwiftUI 会重新渲染视图，更新文本和背景颜色以匹配当前索引：

```swift
struct StepperView: View {
    @State private var value = 0
    let colors: [Color] = [.orange, .red, .gray, .blue, .green,
                           .purple, .pink]

    func incrementStep() {
        value += 1
        if value >= colors.count { value = 0 }
    }

    func decrementStep() {
        value -= 1
        if value < 0 { value = colors.count - 1 }
    }

    var body: some View {
        Stepper(onIncrement: incrementStep,
            onDecrement: decrementStep) {
            Text("Value: \(value) Color: \(colors[value].description)")
        }
        .padding(5)
        .background(colors[value])
    }
```

}



## 过时的初始化器

- **init(value:step:onEditingChanged:label:)**：创建步进器，配置为使用您提供的步进值递增或递减绑定值。
- **init(value:in:step:onEditingChanged:label:)**：创建步进器，配置为使用步长值在您提供的值范围内递增或递减绑定值。


---
source: https://developer.apple.com/documentation/SwiftUI/Stepper/init(onIncrement:onDecrement:onEditingChanged:label:)
crawled: 2025-12-01T10:34:28Z
---

# init(onIncrement:onDecrement:onEditingChanged:label:)

**Initializer**

Creates a stepper instance that performs the closures you provide when the user increments or decrements the stepper.

## Declaration

```swift
nonisolated init(onIncrement: (() -> Void)?, onDecrement: (() -> Void)?, onEditingChanged: @escaping (Bool) -> Void = { _ in }, @ViewBuilder label: () -> Label)
```

## Parameters

- **onIncrement**: The closure to execute when the user clicks or taps the control’s plus button.
- **onDecrement**: The closure to execute when the user clicks or taps the control’s minus button.
- **onEditingChanged**: A closure called when editing begins and ends. For example, on iOS, the user may touch and hold the increment or decrement buttons on a `Stepper` which causes the execution of the `onEditingChanged` closure at the start and end of the gesture.
- **label**: A view describing the purpose of this stepper.

## Discussion

Use this initializer to create a control with a custom title that executes closures you provide when the user clicks or taps the stepper’s increment or decrement buttons.

The example below uses an array that holds a number of [Color](../Color.zh-Hans.md) values, a local state variable, `value`, to set the control’s background color, and title label. When the user clicks or taps on the stepper’s increment or decrement buttons SwiftUI executes the relevant closure that updates `value`, wrapping the `value` to prevent overflow. SwiftUI then re-renders the view, updating the text and background color to match the current index:

```swift
struct StepperView: View {
    @State private var value = 0
    let colors: [Color] = [.orange, .red, .gray, .blue, .green,
                           .purple, .pink]

    func incrementStep() {
        value += 1
        if value >= colors.count { value = 0 }
    }

    func decrementStep() {
        value -= 1
        if value < 0 { value = colors.count - 1 }
    }

    var body: some View {
        Stepper(onIncrement: incrementStep,
            onDecrement: decrementStep) {
            Text("Value: \(value) Color: \(colors[value].description)")
        }
        .padding(5)
        .background(colors[value])
    }
```

}



## Deprecated initializers

- **init(value:step:onEditingChanged:label:)**: Creates a stepper configured to increment or decrement a binding to a value using a step value you provide.
- **init(value:in:step:onEditingChanged:label:)**: Creates a stepper configured to increment or decrement a binding to a value using a step value and within a range of values you provide.

