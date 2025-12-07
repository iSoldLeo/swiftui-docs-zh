---
来源：https://developer.apple.com/documentation/SwiftUI/Stepper/init(_:onIncrement:onDecrement:onEditingChanged:)
抓取时间： 2025-12-01T10:34:26Z
---

# init(_:onIncrement:onDecrement:onEditingChanged:)

**Initializer**

创建使用标题键的步进器，并在用户点击或轻按步进器的递增和递减按钮时执行您提供的闭包。

### 声明

```swift
nonisolated init(_ titleKey: LocalizedStringKey, onIncrement: (() -> Void)?, onDecrement: (() -> Void)?, onEditingChanged: @escaping (Bool) -> Void = { _ in })
```

## 参数

- **titleKey**：步进器本地化标题的关键字，描述步进器的用途。
- **onIncrement**：当用户单击或轻按控件的加号按钮时要执行的闭包。
- **onDecrement**：当用户点击或轻按控件的减号按钮时要执行的闭包。
- **onEditingChanged**：编辑开始和结束时调用的闭包。例如，在 iOS 上，用户可以触摸并按住`Stepper`上的递增或递减按钮，从而在手势开始和结束时执行`onEditingChanged`闭包。

## 讨论

使用该初始化程序可创建一个带有自定义标题的步进器，当按下步进器的递增或递减按钮时，该步进器将执行您提供的闭包。这个版本的[Stepper](../Stepper.zh-Hans.md)不接受与数值的绑定，也不允许您指定可接受的数值范围或步长值--它只是在按下控件的按钮时调用您提供的闭包。

下面的示例使用了一个数组来保存一些[Color](../Color.zh-Hans.md) 值、一个本地状态变量`value`，以设置控件的背景颜色和标题标签。当用户点击或轻按步进器的递增或递减按钮时，SwiftUI 会执行相关的闭包，更新`value`，并封装`value`，以防止溢出。然后，SwiftUI 会重新渲染视图，更新文本和背景颜色以匹配当前索引：

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
        Stepper("Value: \(value) Color: \(colors[value].description)",
                 onIncrement: incrementStep,
                 onDecrement: decrementStep)
        .padding(5)
        .background(colors[value])
    }
}
```



## 创建具有变化行为的步进器

- **init(label:onIncrement:onDecrement:onEditingChanged:)**：创建一个步进器实例，当用户递增或递减步进器时，该实例将执行您提供的闭包。


---
source: https://developer.apple.com/documentation/SwiftUI/Stepper/init(_:onIncrement:onDecrement:onEditingChanged:)
crawled: 2025-12-01T10:34:26Z
---

# init(_:onIncrement:onDecrement:onEditingChanged:)

**Initializer**

Creates a stepper that uses a title key and executes the closures you provide when the user clicks or taps the stepper’s increment and decrement buttons.

## Declaration

```swift
nonisolated init(_ titleKey: LocalizedStringKey, onIncrement: (() -> Void)?, onDecrement: (() -> Void)?, onEditingChanged: @escaping (Bool) -> Void = { _ in })
```

## Parameters

- **titleKey**: The key for the stepper’s localized title describing the purpose of the stepper.
- **onIncrement**: The closure to execute when the user clicks or taps the control’s plus button.
- **onDecrement**: The closure to execute when the user clicks or taps the control’s minus button.
- **onEditingChanged**: A closure that’s called when editing begins and ends. For example, on iOS, the user may touch and hold the increment or decrement buttons on a `Stepper` which causes the execution of the `onEditingChanged` closure at the start and end of the gesture.

## Discussion

Use this initializer to create a stepper with a custom title that executes closures you provide when either of the stepper’s increment or decrement buttons are pressed. This version of [Stepper](../Stepper.zh-Hans.md) doesn’t take a binding to a value, nor does it allow you to specify a range of acceptable values, or a step value – it simply calls the closures you provide when the control’s buttons are pressed.

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
        Stepper("Value: \(value) Color: \(colors[value].description)",
                 onIncrement: incrementStep,
                 onDecrement: decrementStep)
        .padding(5)
        .background(colors[value])
    }
}
```



## Creating a stepper with change behavior

- **init(label:onIncrement:onDecrement:onEditingChanged:)**: Creates a stepper instance that performs the closures you provide when the user increments or decrements the stepper.

