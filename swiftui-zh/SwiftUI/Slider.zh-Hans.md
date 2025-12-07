--- 来源：https://developer.apple.com/documentation/SwiftUI/Slider
抓取时间：2025-12-02T16:24:25Z

---

# 滑块

**Structure**

用于从有界线性值范围内选择值的控件。

## 声明

```swift
struct Slider<Label, ValueLabel> where Label : View, ValueLabel : View
```

## 概述

滑块由一个“滑块”图像组成，用户可以在一条线性“轨道”的两端之间移动该图像。轨道的两端分别代表最小值和最大值。当用户移动滑块时，滑块会更新其绑定值。

以下示例展示了一个绑定到值 `speed` 的滑块。当滑块更新此值时，绑定视图 [Text](Text.zh-Hans.md) 会显示该值的更新。传递给滑块的 `onEditingChanged` 闭包会在用户拖动滑块时接收回调。示例使用此闭包来更改值文本的颜色。

```swift
@State private var speed = 50.0
@State private var isEditing = false

var body: some View {
    VStack {
        Slider(
            value: $speed,
            in: 0...100,
            onEditingChanged: { editing in
                isEditing = editing
            }
        )
        Text("\(speed)")
            .foregroundColor(isEditing ? .red : .blue)
    }
}
```

您还可以使用 `step` 参数来提供滑块路径上的增量步长。例如，如果您有一个范围为 `0` 到 `100` 的滑块，并且您将 `step` 的值设置为 `5`，则滑块的增量将为 `0`、`5`、`10` 等等。以下示例展示了这种方法，并添加了可选的最小值和最大值标签。

```swift
@State private var speed = 50.0
@State private var isEditing = false

var body: some View {
    Slider(
        value: $speed,
        in: 0...100,
        step: 5
    ) {
        Text("Speed")
    } minimumValueLabel: {
        Text("0")
    } maximumValueLabel: {
        Text("100")
    } onEditingChanged: { editing in
        isEditing = editing
    }
    Text("\(speed)")
        .foregroundColor(isEditing ? .red : .blue)
}
```

当 VoiceOver 用户使用语音命令调整滑块时，滑块还会使用 `step` 来增加或减少数值。

## 创建滑块

- **init(value:in:onEditingChanged:)**：创建一个滑块，用于从给定范围内选择数值。

- **init(value:in:step:onEditingChanged:)**：创建一个滑块，用于从给定范围内选择数值，并可设置步长增量。

## 创建带标签的滑块

- **init(value:in:label:onEditingChanged:)**：创建一个滑块，用于从给定范围内选择数值，并显示提供的标签。

- **init(value:in:step:label:onEditingChanged:)**：创建一个滑块，用于从给定范围内选择数值，并可设置步长增量，并显示提供的标签。

- **init(value:in:label:minimumValueLabel:maximumValueLabel:onEditingChanged:)**：创建一个滑块，用于从给定范围内选择一个值，并显示提供的标签。

- **init(value:in:step:label:minimumValueLabel:maximumValueLabel:onEditingChanged:)**：创建一个滑块，用于从给定范围内选择一个值，并按步长递增，并显示提供的标签。

## 为滑块添加刻度

- **SliderTick**：滑块中刻度的表示形式，带有关联的值和可选标签。

- **SliderTickBuilder**：一个结果构建器，用于构造 `SliderTick`，以便在创建 `Slider` 时使用。

- **SliderTickContentForEach**：一种滑块内容类型，通过遍历集合来创建内容。

- **TupleSliderTickContent**：由 Swift 滑块内容元组创建的滑块内容。

- **SliderTickContent**：为 `SliderTickBuilder` 提供内容的类型。

## 已弃用的初始化器

- **init(value:in:onEditingChanged:label:)**：创建一个滑块，用于从给定范围内选择一个值，并显示提供的标签。

- **init(value:in:step:onEditingChanged:label:)**：创建一个滑块，用于从给定范围内选择一个值，并按步长递增，并显示提供的标签。

- **init(value:in:onEditingChanged:minimumValueLabel:maximumValueLabel:label:)**：创建一个滑块，用于从给定范围内选择一个值，并显示提供的标签。

- **init(value:in:step:onEditingChanged:minimumValueLabel:maximumValueLabel:label:)**：创建一个滑块，用于从给定范围内选择一个值，并按步长递增，并显示提供的标签。

## 初始化器

- **init(value:in:neutralValue:enabledBounds:label:currentValueLabel:minimumValueLabel:maximumValueLabel:onEditingChanged:)**：创建一个滑块，用于从给定范围内选择值，并显示提供的标签。

- **init(value:in:neutralValue:enabledBounds:label:currentValueLabel:minimumValueLabel:maximumValueLabel:ticks:onEditingChanged:)**：创建一个滑块，用于从给定范围内选择值，并显示提供的标签和自定义刻度。

- **init(value:in:step:neutralValue:enabledBounds:label:currentValueLabel:minimumValueLabel:maximumValueLabel:tick:onEditingChanged:)**：创建一个滑块，用于从给定范围内选择值，并可按步长递增，并显示提供的标签和可自定义的刻度。

## 获取数值输入

- **Stepper**：一个用于执行递增和递减操作的控件。

- **Toggle**：一个用于在开和关状态之间切换的控件。

- **toggleStyle(_:)**：设置视图层次结构中切换按钮的样式。

## 符合以下视图

- 视图


---
source: https://developer.apple.com/documentation/SwiftUI/Slider
crawled: 2025-12-02T16:24:25Z
---

# Slider

**Structure**

A control for selecting a value from a bounded linear range of values.

## Declaration

```swift
struct Slider<Label, ValueLabel> where Label : View, ValueLabel : View
```

## Overview

A slider consists of a “thumb” image that the user moves between two extremes of a linear “track”. The ends of the track represent the minimum and maximum possible values. As the user moves the thumb, the slider updates its bound value.

The following example shows a slider bound to the value `speed`. As the slider updates this value, a bound [Text](Text.zh-Hans.md) view shows the value updating. The `onEditingChanged` closure passed to the slider receives callbacks when the user drags the slider. The example uses this to change the color of the value text.

```swift
@State private var speed = 50.0
@State private var isEditing = false

var body: some View {
    VStack {
        Slider(
            value: $speed,
            in: 0...100,
            onEditingChanged: { editing in
                isEditing = editing
            }
        )
        Text("\(speed)")
            .foregroundColor(isEditing ? .red : .blue)
    }
}
```



You can also use a `step` parameter to provide incremental steps along the path of the slider. For example, if you have a slider with a range of `0` to `100`, and you set the `step` value to `5`, the slider’s increments would be `0`, `5`, `10`, and so on. The following example shows this approach, and also adds optional minimum and maximum value labels.

```swift
@State private var speed = 50.0
@State private var isEditing = false

var body: some View {
    Slider(
        value: $speed,
        in: 0...100,
        step: 5
    ) {
        Text("Speed")
    } minimumValueLabel: {
        Text("0")
    } maximumValueLabel: {
        Text("100")
    } onEditingChanged: { editing in
        isEditing = editing
    }
    Text("\(speed)")
        .foregroundColor(isEditing ? .red : .blue)
}
```



The slider also uses the `step` to increase or decrease the value when a VoiceOver user adjusts the slider with voice commands.

## Creating a slider

- **init(value:in:onEditingChanged:)**: Creates a slider to select a value from a given range.
- **init(value:in:step:onEditingChanged:)**: Creates a slider to select a value from a given range, subject to a step increment.

## Creating a slider with labels

- **init(value:in:label:onEditingChanged:)**: Creates a slider to select a value from a given range, which displays the provided label.
- **init(value:in:step:label:onEditingChanged:)**: Creates a slider to select a value from a given range, subject to a step increment, which displays the provided label.
- **init(value:in:label:minimumValueLabel:maximumValueLabel:onEditingChanged:)**: Creates a slider to select a value from a given range, which displays the provided labels.
- **init(value:in:step:label:minimumValueLabel:maximumValueLabel:onEditingChanged:)**: Creates a slider to select a value from a given range, subject to a step increment, which displays the provided labels.

## Adding ticks to a slider

- **SliderTick**: A representation of a tick in a slider, with associated value and optional label.
- **SliderTickBuilder**: A result builder that constructs `SliderTick`s for use when creating a `Slider`.
- **SliderTickContentForEach**: A type of slider content that creates content by iterating over a collection.
- **TupleSliderTickContent**: Slider content created from a Swift tuple of slider content.
- **SliderTickContent**: A type that provides content for a `SliderTickBuilder`.

## Deprecated initializers

- **init(value:in:onEditingChanged:label:)**: Creates a slider to select a value from a given range, which displays the provided label.
- **init(value:in:step:onEditingChanged:label:)**: Creates a slider to select a value from a given range, subject to a step increment, which displays the provided label.
- **init(value:in:onEditingChanged:minimumValueLabel:maximumValueLabel:label:)**: Creates a slider to select a value from a given range, which displays the provided labels.
- **init(value:in:step:onEditingChanged:minimumValueLabel:maximumValueLabel:label:)**: Creates a slider to select a value from a given range, subject to a step increment, which displays the provided labels.

## Initializers

- **init(value:in:neutralValue:enabledBounds:label:currentValueLabel:minimumValueLabel:maximumValueLabel:onEditingChanged:)**: Creates a slider to select a value from a given range, which displays the provided labels.
- **init(value:in:neutralValue:enabledBounds:label:currentValueLabel:minimumValueLabel:maximumValueLabel:ticks:onEditingChanged:)**: Creates a slider to select a value from a given range, which displays the provided labels and customized ticks.
- **init(value:in:step:neutralValue:enabledBounds:label:currentValueLabel:minimumValueLabel:maximumValueLabel:tick:onEditingChanged:)**: Creates a slider to select a value from a given range, subject to a step increment, which displays the provided labels and customizable ticks.

## Getting numeric inputs

- **Stepper**: A control that performs increment and decrement actions.
- **Toggle**: A control that toggles between on and off states.
- **toggleStyle(_:)**: Sets the style for toggles in a view hierarchy.

## Conforms To

- View

