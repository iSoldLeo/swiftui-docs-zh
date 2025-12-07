---
来源：https://developer.apple.com/documentation/SwiftUI/Stepper/init(label:onIncrement:onDecrement:onEditingChanged:)
抓取时间： 2025-12-03T05:45:12Z


# init(label:onIncrement:onDecrement:onEditingChanged:)

**Initializer**

创建步进器实例，当用户递增或递减步进器时执行您提供的闭包。

## 声明

```swift
init(@ViewBuilder label: () -> Label, onIncrement: (() -> Void)?, onDecrement: (() -> Void)?, onEditingChanged: @escaping (Bool) -> Void = { _ in })
```

## 参数

- **label**：描述该步进器用途的视图。
- **onIncrement**：当用户单击或轻按控件的加号按钮时要执行的闭包。
- **onDecrement**：当用户点击或轻按控件的减号按钮时要执行的闭包。
- **onEditingChanged**：编辑开始和结束时调用的闭包。例如，在 iOS 上，用户可以触摸并按住`Stepper`上的递增或递减按钮，从而在手势开始和结束时执行`onEditingChanged`闭包。

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
        Stepper {
            Text("Value: \(value) Color: \(colors[value].description)")
        } onIncrement: {
            incrementStep()
        } onDecrement: {
            decrementStep()
        }
        .padding(5)
        .background(colors[value])
    }
```

}



## 创建具有变化行为的步进器

- **init(_:onIncrement:onDecrement:onEditingChanged:)**：创建一个使用标题键的步进器，当用户点击或轻按步进器的递增和递减按钮时，执行您提供的闭包。


---
source: https://developer.apple.com/documentation/SwiftUI/Stepper/init(label:onIncrement:onDecrement:onEditingChanged:)
crawled: 2025-12-03T05:45:12Z
---

# init(label:onIncrement:onDecrement:onEditingChanged:)

**Initializer**

Creates a stepper instance that performs the closures you provide when the user increments or decrements the stepper.

## Declaration

```swift
init(@ViewBuilder label: () -> Label, onIncrement: (() -> Void)?, onDecrement: (() -> Void)?, onEditingChanged: @escaping (Bool) -> Void = { _ in })
```

## Parameters

- **label**: A view describing the purpose of this stepper.
- **onIncrement**: The closure to execute when the user clicks or taps the control’s plus button.
- **onDecrement**: The closure to execute when the user clicks or taps the control’s minus button.
- **onEditingChanged**: A closure called when editing begins and ends. For example, on iOS, the user may touch and hold the increment or decrement buttons on a `Stepper` which causes the execution of the `onEditingChanged` closure at the start and end of the gesture.

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
        Stepper {
            Text("Value: \(value) Color: \(colors[value].description)")
        } onIncrement: {
            incrementStep()
        } onDecrement: {
            decrementStep()
        }
        .padding(5)
        .background(colors[value])
    }
```

}



## Creating a stepper with change behavior

- **init(_:onIncrement:onDecrement:onEditingChanged:)**: Creates a stepper that uses a title key and executes the closures you provide when the user clicks or taps the stepper’s increment and decrement buttons.

