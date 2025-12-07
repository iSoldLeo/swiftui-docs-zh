--- 来源：https://developer.apple.com/documentation/swiftui/slidertick
抓取时间：2025-12-05T08:57:56Z

---

# SliderTick

**Structure**

滑块刻度线的表示，带有关联的值和可选的标签。

## 声明

```swift
struct SliderTick<V> where V : BinaryFloatingPoint
```

## 概述

以下示例展示了一个绑定到值 `percentage` 的滑块。当滑块更新时，`currentValueLabel` 也会更新。滑块还会以 `0.25` 的步长间隔渲染标记。

```swift
@State private var percentage = 0.5

Slider(value: $percentage) {
    Text("Percentage")
} currentValueLabel: {
    Text("\(percentage)%")
} ticks: {
    SliderTickContentForEach(
        stride(from: 0.0, through: 1.0, by: 0.25).map { $0 },
        id: \.self
    ) { value in
        SliderTick(value) {
            label(for: value)
        }
    }
}
```

## 结构体

- **SliderTick.ID**：刻度线的标识。

## 初始化器

- **init(_:)**：在指定值处创建带标签的滑块刻度。

- **init(_:_:)**：使用本地化字符串键创建带标签的滑块刻度。

- **init(_:label:)**：在指定值处创建带标签的滑块刻度。

## 实例属性

- **id**：刻度的标识，由其值派生而来。

## 向滑块添加刻度

- **SliderTickBuilder**：结果构建器，用于构造 `SliderTick`，以便在创建 `Slider` 时使用。

- **SliderTickContentForEach**：一种滑块内容类型，通过遍历集合来创建内容。

- **TupleSliderTickContent**：由 Swift 滑块内容元组创建的滑块内容。

- **SliderTickContent**：为 `SliderTickBuilder` 提供内容的类型。

## 符合以下规范

- Comparable

- Equatable

- Identifiable

- SliderTickContent


---
source: https://developer.apple.com/documentation/swiftui/slidertick
crawled: 2025-12-05T08:57:56Z
---

# SliderTick

**Structure**

A representation of a tick in a slider, with associated value and optional label.

## Declaration

```swift
struct SliderTick<V> where V : BinaryFloatingPoint
```

## Overview

The following example shows a slider bound to the value `percentage`. As the slider updates the `currentValueLabel`. The slider also renders marks at a `0.25` step interval.

```swift
@State private var percentage = 0.5

Slider(value: $percentage) {
    Text("Percentage")
} currentValueLabel: {
    Text("\(percentage)%")
} ticks: {
    SliderTickContentForEach(
        stride(from: 0.0, through: 1.0, by: 0.25).map { $0 },
        id: \.self
    ) { value in
        SliderTick(value) {
            label(for: value)
        }
    }
}
```

## Structures

- **SliderTick.ID**: The identity of a tick.

## Initializers

- **init(_:)**: Create a labeled slider tick at a specific value.
- **init(_:_:)**: Create a slider tick with a label from a localized string key.
- **init(_:label:)**: Create a labeled slider tick at a specific value.

## Instance Properties

- **id**: The identity of a tick, which is derived from its value.

## Adding ticks to a slider

- **SliderTickBuilder**: A result builder that constructs `SliderTick`s for use when creating a `Slider`.
- **SliderTickContentForEach**: A type of slider content that creates content by iterating over a collection.
- **TupleSliderTickContent**: Slider content created from a Swift tuple of slider content.
- **SliderTickContent**: A type that provides content for a `SliderTickBuilder`.

## Conforms To

- Comparable
- Equatable
- Identifiable
- SliderTickContent

