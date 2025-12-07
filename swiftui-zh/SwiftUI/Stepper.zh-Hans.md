---
来源： https://developer.apple.com/documentation/SwiftUI/Stepper
抓取时间： 2025-12-02T17:27:52Z
---

# 步进器

**Structure**

执行递增和递减操作的控件。

### 声明

```swift
struct Stepper<Label> where Label : View
```

## 概览

如果希望用户在递增或递减数值时进行细粒度控制，可以使用步进控制。例如，您可以使用步进控制来

- 以 `1` 的幅度增减数值。
- 严格在规定范围内运行。
- 在步进器的可能取值范围内按特定量步进。

下面的示例使用了一个数组来保存一些[Color](Color.zh-Hans.md) 值、一个本地状态变量`value`，以设置控件的背景颜色和标题标签。当用户点击或轻按步进器的递增或递减按钮时，SwiftUI 会执行相关的闭包，更新`value`，并包裹`value`，以防止溢出。然后，SwiftUI 会重新渲染视图，更新文本和背景颜色以匹配当前索引：

```swift
struct StepperView: View {
    @State private var value = 0
    let colors: [Color] = [.orange, .red, .gray, .blue,
                           .green, .purple, .pink]

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
}
```



下面的示例显示了一个步进器，该步进器显示以 `step` 步长递增或递减数值的效果，其边界由 `range` 定义：

```swift
struct StepperView: View {
    @State private var value = 0
    let step = 5
    let range = 1...50

    var body: some View {
        Stepper(
            value: $value,
            in: range,
            step: step
        ) {
            Text("Current: \(value) in \(range.description) " +
                 "stepping by \(step)")
        }
        .padding(10)
    }
}
```



## 创建步进器

- **init(value:step:label:onEditingChanged:)**：创建步进器，配置为使用您提供的步长值将绑定值递增或递减。
- **init(value:step:format:label:onEditingChanged:)**：创建一个步进器，该步进器被配置为使用您提供的步长值递增或递减绑定值，并使用应用的格式样式显示其值。
- **init(_:value:step:onEditingChanged:)**：创建带标题的步进器，并配置为按您提供的值和步进量递增和递减绑定。
- **init(_:value:step:format:onEditingChanged:)**：创建带有标题键的步进器，并配置为按您提供的值和步长递增和递减绑定，用应用的格式样式显示其值。

## 在一个范围内创建步进器

- **init(value:in:step:label:onEditingChanged:)**：创建步进器，配置为使用步进值并在您提供的值范围内递增或递减绑定值。
- **init(value:in:step:format:label:onEditingChanged:)**：创建步进器，配置为使用步进值在您提供的值范围内递增或递减绑定值，并使用应用的格式样式显示其值。
- **init(_:value:in:step:onEditingChanged:)**：创建一个步进实例，在您提供的封闭范围内，按步进大小递增或递减绑定值。
- **init(_:value:in:step:format:onEditingChanged:)**：创建一个步进器实例，在您提供的封闭范围内按步长递增和递减绑定值，并以应用的格式样式显示其值。

## 创建具有变化行为的步进器

- **init(label:onIncrement:onDecrement:onEditingChanged:)**：创建一个步进器实例，当用户递增或递减步进器时，该实例将执行您提供的闭包。
- **init(_:onIncrement:onDecrement:onEditingChanged:)**：创建使用标题键的步进器，并在用户单击或轻按步进器的递增和递减按钮时执行您提供的闭包。

## 过时的初始化程序

- **init(value:step:onEditingChanged:label:)**：创建步进器，配置为使用您提供的步长值对绑定值进行递增或递减。
- **init(value:in:step:onEditingChanged:label:)**：创建一个步进器，该步进器被配置为使用步长值并在您提供的值范围内递增或递减绑定值。
- **init(onIncrement:onDecrement:onEditingChanged:label:)**：创建步进器实例，在用户递增或递减步进器时执行您提供的闭合。

## 获取数字输入

- **Slider**：从有界线性范围内选择数值的控件。
- **Toggle**：在开启和关闭状态之间切换的控件。
- **toggleStyle(_:)**：设置视图层次结构中的切换样式。

## 符合

- 视图


---
source: https://developer.apple.com/documentation/SwiftUI/Stepper
crawled: 2025-12-02T17:27:52Z
---

# Stepper

**Structure**

A control that performs increment and decrement actions.

## Declaration

```swift
struct Stepper<Label> where Label : View
```

## Overview

Use a stepper control when you want the user to have granular control while incrementing or decrementing a value. For example, you can use a stepper to:

- Change a value up or down by `1`.
- Operate strictly over a prescribed range.
- Step by specific amounts over a stepper’s range of possible values.

The example below uses an array that holds a number of [Color](Color.zh-Hans.md) values, a local state variable, `value`, to set the control’s background color, and title label. When the user clicks or taps the stepper’s increment or decrement buttons, SwiftUI executes the relevant closure that updates `value`, wrapping the `value` to prevent overflow. SwiftUI then re-renders the view, updating the text and background color to match the current index:

```swift
struct StepperView: View {
    @State private var value = 0
    let colors: [Color] = [.orange, .red, .gray, .blue,
                           .green, .purple, .pink]

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
}
```



The following example shows a stepper that displays the effect of incrementing or decrementing a value with the step size of `step` with the bounds defined by `range`:

```swift
struct StepperView: View {
    @State private var value = 0
    let step = 5
    let range = 1...50

    var body: some View {
        Stepper(
            value: $value,
            in: range,
            step: step
        ) {
            Text("Current: \(value) in \(range.description) " +
                 "stepping by \(step)")
        }
        .padding(10)
    }
}
```



## Creating a stepper

- **init(value:step:label:onEditingChanged:)**: Creates a stepper configured to increment or decrement a binding to a value using a step value you provide.
- **init(value:step:format:label:onEditingChanged:)**: Creates a stepper configured to increment or decrement a binding to a value using a step value you provide, displaying its value with an applied format style.
- **init(_:value:step:onEditingChanged:)**: Creates a stepper with a title and configured to increment and decrement a binding to a value and step amount you provide.
- **init(_:value:step:format:onEditingChanged:)**: Creates a stepper with a title key and configured to increment and decrement a binding to a value and step amount you provide, displaying its value with an applied format style.

## Creating a stepper over a range

- **init(value:in:step:label:onEditingChanged:)**: Creates a stepper configured to increment or decrement a binding to a value using a step value and within a range of values you provide.
- **init(value:in:step:format:label:onEditingChanged:)**: Creates a stepper configured to increment or decrement a binding to a value using a step value and within a range of values you provide, displaying its value with an applied format style.
- **init(_:value:in:step:onEditingChanged:)**: Creates a stepper instance that increments and decrements a binding to a value, by a step size and within a closed range that you provide.
- **init(_:value:in:step:format:onEditingChanged:)**: Creates a stepper instance that increments and decrements a binding to a value, by a step size and within a closed range that you provide, displaying its value with an applied format style.

## Creating a stepper with change behavior

- **init(label:onIncrement:onDecrement:onEditingChanged:)**: Creates a stepper instance that performs the closures you provide when the user increments or decrements the stepper.
- **init(_:onIncrement:onDecrement:onEditingChanged:)**: Creates a stepper that uses a title key and executes the closures you provide when the user clicks or taps the stepper’s increment and decrement buttons.

## Deprecated initializers

- **init(value:step:onEditingChanged:label:)**: Creates a stepper configured to increment or decrement a binding to a value using a step value you provide.
- **init(value:in:step:onEditingChanged:label:)**: Creates a stepper configured to increment or decrement a binding to a value using a step value and within a range of values you provide.
- **init(onIncrement:onDecrement:onEditingChanged:label:)**: Creates a stepper instance that performs the closures you provide when the user increments or decrements the stepper.

## Getting numeric inputs

- **Slider**: A control for selecting a value from a bounded linear range of values.
- **Toggle**: A control that toggles between on and off states.
- **toggleStyle(_:)**: Sets the style for toggles in a view hierarchy.

## Conforms To

- View

