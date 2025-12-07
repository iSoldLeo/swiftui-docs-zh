---
来源：https://developer.apple.com/documentation/SwiftUI/SliderTickContentForEach/init(_:id:content:)
抓取时间： 2025-12-02T01:12:20Z
---

# init(_:id:content:)

**Initializer**

创建一个实例，根据提供的底层数据标识符关键路径，在更新时唯一标识和创建滑块刻度。

### 声明

```swift
nonisolated init<V>(_ data: Data, id: KeyPath<Data.Element, ID>, @SliderTickBuilder<V> content: @escaping (Data.Element) -> Content) where V == Data.Element, Data.Element == Content.Value
```

## 参数

- **data**：[ForEach](../ForEach.zh-Hans.md)实例用于动态创建标记项的数据。
- **id**：所提供数据标识符的关键路径。
- **content**：动态创建刻度的生成器。

## 讨论

重要的是，数据元素的 `id` 不能改变，除非 SwiftUI 认为该数据元素已被具有新标识的新数据元素替换。如果数据元素的`id` 发生变化，那么由该数据元素生成的标记将丢失任何当前状态和动画。


---
source: https://developer.apple.com/documentation/SwiftUI/SliderTickContentForEach/init(_:id:content:)
crawled: 2025-12-02T01:12:20Z
---

# init(_:id:content:)

**Initializer**

Creates an instance that uniquely identifies and creates slider ticks across updates based on the provided key path to the underlying data’s identifier.

## Declaration

```swift
nonisolated init<V>(_ data: Data, id: KeyPath<Data.Element, ID>, @SliderTickBuilder<V> content: @escaping (Data.Element) -> Content) where V == Data.Element, Data.Element == Content.Value
```

## Parameters

- **data**: The data that the [ForEach](../ForEach.zh-Hans.md) instance uses to create mark items dynamically.
- **id**: The key path to the provided data’s identifier.
- **content**: The builder that creates ticks dynamically.

## Discussion

It’s important that the `id` of a data element doesn’t change, unless SwiftUI considers the data element to have been replaced with a new data element that has a new identity. If the `id` of a data element changes, then the marks generated from that data element will lose any current state and animations.

