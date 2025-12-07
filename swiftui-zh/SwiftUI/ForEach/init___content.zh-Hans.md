---
来源： https://developer.apple.com/documentation/SwiftUI/ForEach/init(_:content:)
抓取时间： 2025-12-01T00:43:50Z
---

# init(_:content:)

**Initializer**

创建一个实例，根据底层数据的身份在更新时唯一标识和创建地图内容。

### 声明

```swift
@MainActor init(_ data: Data, @MapContentBuilder content: @escaping (Data.Element) -> Content) where ID == Data.Element.ID, Data.Element : Identifiable
```

## 参数

- **data**：[ForEach](../ForEach.zh-Hans.md)实例用于动态创建地图内容的标识数据。
- **content**：动态创建地图内容的地图内容生成器。

## 讨论

重要的是，数据元素的`id` 不能改变，除非用具有新标识的新数据元素替换该数据元素。如果数据元素的`id` 发生变化，由该数据元素生成的内容视图将丢失任何当前状态和动画。

## 创建一个集合

- **init(_:)**：创建一个实例，根据基础数据的身份唯一标识并在更新时创建表行。
- **init(_:id:content:)**：创建一个实例，该实例可根据所提供的底层数据标识符的键路径，在更新时唯一标识和创建映射内容。


---
source: https://developer.apple.com/documentation/SwiftUI/ForEach/init(_:content:)
crawled: 2025-12-01T00:43:50Z
---

# init(_:content:)

**Initializer**

Creates an instance that uniquely identifies and creates map content across updates based on the identity of the underlying data.

## Declaration

```swift
@MainActor init(_ data: Data, @MapContentBuilder content: @escaping (Data.Element) -> Content) where ID == Data.Element.ID, Data.Element : Identifiable
```

## Parameters

- **data**: The identified data that the [ForEach](../ForEach.zh-Hans.md) instance uses to create map content dynamically.
- **content**: The map content builder that creates map content dynamically.

## Discussion

It’s important that the `id` of a data element doesn’t change unless you replace the data element with a new data element that has a new identity. If the `id` of a data element changes, the content view generated from that data element loses any current state and animations.

## Creating a collection

- **init(_:)**: Creates an instance that uniquely identifies and creates table rows across updates based on the identity of the underlying data.
- **init(_:id:content:)**: Creates an instance that uniquely identifies and creates map content across updates based on the provided key path to the underlying data’s identifier.

