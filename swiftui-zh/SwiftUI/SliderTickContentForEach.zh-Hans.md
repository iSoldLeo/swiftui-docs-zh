--- 来源：https://developer.apple.com/documentation/SwiftUI/SliderTickContentForEach
抓取时间：2025-12-02T21:57:45Z

---

# SliderTickContentForEach

**Structure**

一种通过遍历集合来创建内容的滑块内容类型。

## 声明

```swift
struct SliderTickContentForEach<Data, ID, Content> where Data : RandomAccessCollection, ID : Hashable, Content : SliderTickContent
```

## 初始化器

- **init(_:content:)**：创建一个实例，该实例基于底层数据的标识，在更新过程中唯一标识并创建滑块刻度。

- **init(_:id:content:)**：创建一个实例，该实例基于指向底层数据标识符的键路径，在更新过程中唯一标识并创建滑块刻度。

## 为滑块添加刻度

- **SliderTick**：滑块刻度的表示形式，包含关联值和可选标签。

- **SliderTickBuilder**：用于构建 `SliderTick` 的结果构建器，以便在创建 `Slider` 时使用。

- **TupleSliderTickContent**：由 Swift 滑块内容元组创建的滑块内容。

- **SliderTickContent**：为 `SliderTickBuilder` 提供内容的类型。

## 符合以下规范

- SliderTickContent


---
source: https://developer.apple.com/documentation/SwiftUI/SliderTickContentForEach
crawled: 2025-12-02T21:57:45Z
---

# SliderTickContentForEach

**Structure**

A type of slider content that creates content by iterating over a collection.

## Declaration

```swift
struct SliderTickContentForEach<Data, ID, Content> where Data : RandomAccessCollection, ID : Hashable, Content : SliderTickContent
```

## Initializers

- **init(_:content:)**: Creates an instance that uniquely identifies and creates slider ticks across updates based on the identity of the underlying data.
- **init(_:id:content:)**: Creates an instance that uniquely identifies and creates slider ticks across updates based on the provided key path to the underlying data’s identifier.

## Adding ticks to a slider

- **SliderTick**: A representation of a tick in a slider, with associated value and optional label.
- **SliderTickBuilder**: A result builder that constructs `SliderTick`s for use when creating a `Slider`.
- **TupleSliderTickContent**: Slider content created from a Swift tuple of slider content.
- **SliderTickContent**: A type that provides content for a `SliderTickBuilder`.

## Conforms To

- SliderTickContent

