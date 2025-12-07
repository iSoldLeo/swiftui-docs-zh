--- 来源：https://developer.apple.com/documentation/swiftui/slidertickbuilder
抓取时间：2025-12-05T08:57:47Z

---

# SliderTickBuilder

**Structure**

一个结果构建器，用于构造 `SliderTick`，以便在创建 `Slider` 时使用。

## 声明

```swift
@resultBuilder struct SliderTickBuilder<V> where V : BinaryFloatingPoint
```

## 类型方法

- **buildBlock()**：创建单个滑块内容结果。

- **buildBlock(_:)**：创建单个滑块内容结果。

- **buildBlock(_:_:)**

- **buildBlock(_:_:_:)**

- **buildBlock(_:_:_:_:)**

- **buildBlock(_:_:_:_:_:)**

- **buildBlock(_:_:_:_:_:_:)**

- **buildBlock(_:_:_:_:_:_:_:)**

- **buildBlock(_:_:_:_:_:_:_:_:)**

- **buildBlock(_:_:_:_:_:_:_:_:_:)**

- **buildBlock(_:_:_:_:_:_:_:_:_:_:)**

- **buildEither(first:)**：当条件为真时，为多语句闭包中的条件语句生成内容。

- **buildEither(second:)**：当条件为假时，为多语句闭包中的条件语句生成内容。

- **buildExpression(_:)**：创建单个滑块内容表达式。

- **buildIf(_:)**：为多语句闭包中的条件语句生成可选的滑块内容，该内容仅在条件为真时可见。

## 为滑块添加刻度

- **SliderTick**：滑块中刻度的表示形式，带有关联的值和可选标签。

- **SliderTickContentForEach**：一种通过遍历集合创建内容的滑块内容类型。

- **TupleSliderTickContent**：由 Swift 滑块内容元组创建的滑块内容。

- **SliderTickContent**：一种为 `SliderTickBuilder` 提供内容的类型。


---
source: https://developer.apple.com/documentation/swiftui/slidertickbuilder
crawled: 2025-12-05T08:57:47Z
---

# SliderTickBuilder

**Structure**

A result builder that constructs `SliderTick`s for use when creating a `Slider`.

## Declaration

```swift
@resultBuilder struct SliderTickBuilder<V> where V : BinaryFloatingPoint
```

## Type Methods

- **buildBlock()**: Creates a single slider content result.
- **buildBlock(_:)**: Creates a single slider content result.
- **buildBlock(_:_:)**
- **buildBlock(_:_:_:)**
- **buildBlock(_:_:_:_:)**
- **buildBlock(_:_:_:_:_:)**
- **buildBlock(_:_:_:_:_:_:)**
- **buildBlock(_:_:_:_:_:_:_:)**
- **buildBlock(_:_:_:_:_:_:_:_:)**
- **buildBlock(_:_:_:_:_:_:_:_:_:)**
- **buildBlock(_:_:_:_:_:_:_:_:_:_:)**
- **buildEither(first:)**: Produces content for a conditional statement in a multi-statement closure when the condition is true.
- **buildEither(second:)**: Produces content for a conditional statement in a multi-statement closure when the condition is false.
- **buildExpression(_:)**: Creates a single slider content expression.
- **buildIf(_:)**: Produces an optional slider content for conditional statements in multi-statement closures that’s only visible when the condition evaluates to true.

## Adding ticks to a slider

- **SliderTick**: A representation of a tick in a slider, with associated value and optional label.
- **SliderTickContentForEach**: A type of slider content that creates content by iterating over a collection.
- **TupleSliderTickContent**: Slider content created from a Swift tuple of slider content.
- **SliderTickContent**: A type that provides content for a `SliderTickBuilder`.

