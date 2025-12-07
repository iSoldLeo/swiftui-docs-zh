--- 来源：https://developer.apple.com/documentation/swiftui/tupleslidertickcontent
抓取时间：2025-12-05T08:57:55Z

---

# TupleSliderTickContent

**Structure**

使用 Swift 元组创建滑块内容。

## 声明

```swift
@frozen struct TupleSliderTickContent<V, T> where V : BinaryFloatingPoint
```

## 实例属性

- **value**

## 类型别名

- **TupleSliderTickContent.TicksCollection**

## 为滑块添加刻度

- **SliderTick**：滑块刻度的表示形式，包含关联值和可选标签。

- **SliderTickBuilder**：一个结果构建器，用于构建 `SliderTick`，以便在创建 `Slider` 时使用。

- **SliderTickContentForEach**：一种滑块内容类型，通过遍历集合来创建内容。

- **SliderTickContent**：一种为 `SliderTickBuilder` 提供内容的类型。

## 符合以下规范

- SliderTickContent


---
source: https://developer.apple.com/documentation/swiftui/tupleslidertickcontent
crawled: 2025-12-05T08:57:55Z
---

# TupleSliderTickContent

**Structure**

Slider content created from a Swift tuple of slider content.

## Declaration

```swift
@frozen struct TupleSliderTickContent<V, T> where V : BinaryFloatingPoint
```

## Instance Properties

- **value**

## Type Aliases

- **TupleSliderTickContent.TicksCollection**

## Adding ticks to a slider

- **SliderTick**: A representation of a tick in a slider, with associated value and optional label.
- **SliderTickBuilder**: A result builder that constructs `SliderTick`s for use when creating a `Slider`.
- **SliderTickContentForEach**: A type of slider content that creates content by iterating over a collection.
- **SliderTickContent**: A type that provides content for a `SliderTickBuilder`.

## Conforms To

- SliderTickContent

