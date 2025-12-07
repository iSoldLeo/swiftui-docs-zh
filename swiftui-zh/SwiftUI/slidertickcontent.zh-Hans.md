--- 来源：https://developer.apple.com/documentation/swiftui/slidertickcontent
抓取时间：2025-12-05T08:57:48Z

---

# SliderTickContent

**Protocol**

为 `SliderTickBuilder` 提供内容的类型。

## 声明

```swift
protocol SliderTickContent<Value>
```

## 关联类型

- **Body**

- **Value**

## 实例属性

- **body**：此类型内容的值。

## 为滑块添加刻度

- **SliderTick**：滑块中刻度的表示形式，带有关联的值和可选的标签。

- **SliderTickBuilder**：一个结果构建器，用于构造 `SliderTick`，以便在创建 `Slider` 时使用。

- **SliderTickContentForEach**：一种滑块内容类型，通过遍历集合来创建内容。

- **TupleSliderTickContent**：由 Swift 滑块内容元组创建的滑块内容。

## 符合规范的类型

- SliderTick

- SliderTickContentForEach

- TupleSliderTickContent


---
source: https://developer.apple.com/documentation/swiftui/slidertickcontent
crawled: 2025-12-05T08:57:48Z
---

# SliderTickContent

**Protocol**

A type that provides content for a `SliderTickBuilder`.

## Declaration

```swift
protocol SliderTickContent<Value>
```

## Associated Types

- **Body**
- **Value**

## Instance Properties

- **body**: The value of this type’s content.

## Adding ticks to a slider

- **SliderTick**: A representation of a tick in a slider, with associated value and optional label.
- **SliderTickBuilder**: A result builder that constructs `SliderTick`s for use when creating a `Slider`.
- **SliderTickContentForEach**: A type of slider content that creates content by iterating over a collection.
- **TupleSliderTickContent**: Slider content created from a Swift tuple of slider content.

## Conforming Types

- SliderTick
- SliderTickContentForEach
- TupleSliderTickContent

