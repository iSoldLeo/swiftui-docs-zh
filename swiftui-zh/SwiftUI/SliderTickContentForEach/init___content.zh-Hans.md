---
来源： https://developer.apple.com/documentation/SwiftUI/SliderTickContentForEach/init(_:content:)
抓取时间： 2025-12-03T20:27:13Z
---

# init(_:content:)

**Initializer**

创建一个实例，根据底层数据的身份唯一标识并在更新时创建滑块刻度。

### 声明

```swift
nonisolated init<V>(_ data: Data, @SliderTickBuilder<V> content: @escaping (Data.Element) -> Content) where ID == V.ID, V : Identifiable, V == Data.Element, Data.Element == Content.Value
```

## 参数

- **data**：[ForEach](../ForEach.zh-Hans.md)实例用于动态创建滑块刻度的标识数据。
- **content**：为每个元素动态创建刻度的构建器。


---
source: https://developer.apple.com/documentation/SwiftUI/SliderTickContentForEach/init(_:content:)
crawled: 2025-12-03T20:27:13Z
---

# init(_:content:)

**Initializer**

Creates an instance that uniquely identifies and creates slider ticks across updates based on the identity of the underlying data.

## Declaration

```swift
nonisolated init<V>(_ data: Data, @SliderTickBuilder<V> content: @escaping (Data.Element) -> Content) where ID == V.ID, V : Identifiable, V == Data.Element, Data.Element == Content.Value
```

## Parameters

- **data**: The identified data that the [ForEach](../ForEach.zh-Hans.md) instance uses to create slider ticks dynamically.
- **content**: The builder that creates ticks dynamically for each element.

