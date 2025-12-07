---
来源：https://developer.apple.com/documentation/SwiftUI/ForEach/init(_:id:content:)
抓取时间： 2025-12-01T00:43:51Z
---

# init(_:id:content:)

**Initializer**

创建一个实例，根据提供的底层数据标识符关键路径，在更新时唯一标识和创建地图内容。

### 声明

```swift
@MainActor init(_ data: Data, id: KeyPath<Data.Element, ID>, @MapContentBuilder content: @escaping (Data.Element) -> Content)
```

## 参数

- **data**：[ForEach](../ForEach.zh-Hans.md)实例用于动态创建地图内容的数据。
- **id**：所提供数据标识符的关键路径。
- **content**：动态创建地图内容的地图内容生成器。

## 讨论

重要的是，数据元素的`id` 不能改变，除非该数据元素已被具有新标识的新数据元素所取代。如果数据元素的`id` 发生变化，那么由该数据元素生成的地图内容将丢失任何当前状态和动画。

## 创建集合

- **init(_:)**：创建一个实例，该实例可根据基础数据的身份唯一标识并在更新时创建表行。
- **init(_:content:)**：创建一个实例，该实例可根据基础数据的标识在更新时唯一标识和创建地图内容。


---
source: https://developer.apple.com/documentation/SwiftUI/ForEach/init(_:id:content:)
crawled: 2025-12-01T00:43:51Z
---

# init(_:id:content:)

**Initializer**

Creates an instance that uniquely identifies and creates map content across updates based on the provided key path to the underlying data’s identifier.

## Declaration

```swift
@MainActor init(_ data: Data, id: KeyPath<Data.Element, ID>, @MapContentBuilder content: @escaping (Data.Element) -> Content)
```

## Parameters

- **data**: The data that the [ForEach](../ForEach.zh-Hans.md) instance uses to create map content dynamically.
- **id**: The key path to the provided data’s identifier.
- **content**: The map content builder that creates map content dynamically.

## Discussion

It’s important that the `id` of a data element doesn’t change, unless the data element has been replaced with a new data element that has a new identity. If the `id` of a data element changes, then the map content generated from that data element will lose any current state and animations.

## Creating a collection

- **init(_:)**: Creates an instance that uniquely identifies and creates table rows across updates based on the identity of the underlying data.
- **init(_:content:)**: Creates an instance that uniquely identifies and creates map content across updates based on the identity of the underlying data.

