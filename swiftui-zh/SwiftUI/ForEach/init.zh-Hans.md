---
来源： https://developer.apple.com/documentation/SwiftUI/ForEach/init(_:)
抓取时间： 2025-12-01T00:43:49Z
---

# init(_:)

**Initializer**

创建一个实例，根据底层数据的身份唯一标识并在更新时创建表格行。

### 声明

```swift
nonisolated init(_ data: Data) where ID == Data.Element.ID, Content == TableRow<Data.Element>, Data.Element : Identifiable
```

## 参数

- **data**：[ForEach](../ForEach.zh-Hans.md)实例用于动态创建表行的标识数据。

## 讨论

下面的示例创建了符合[doc://com.apple.documentation/documentation/Swift/Identifiable] 的`Person` 类型，以及名为`people` 的数组。一个`ForEach` 实例对数组进行迭代，隐式地产生新的[TableRow](../TableRow.zh-Hans.md) 实例。

```swift
private struct Person: Identifiable {
    var id = UUID()
    var name: String
}

@State private var people: [Person] = /* ... */

Table(of: Person.self) {
    TableColumn("ID", value: \.id.uuidString)
    TableColumn("Name", value: \.name)
} rows: {
    Section("Team") {
        /* This is equivalent to the line below:
        ForEach(people) { TableRow($0) }
        */
        ForEach(people)
    }
}
```实例

## 创建一个集合

- **init(_:content:)**：创建一个实例，根据底层数据的身份在更新时唯一标识和创建地图内容。
- **init(_:id:content:)**：创建一个实例，该实例可根据所提供的底层数据标识符关键路径，唯一标识和创建跨更新的映射内容。


---
source: https://developer.apple.com/documentation/SwiftUI/ForEach/init(_:)
crawled: 2025-12-01T00:43:49Z
---

# init(_:)

**Initializer**

Creates an instance that uniquely identifies and creates table rows across updates based on the identity of the underlying data.

## Declaration

```swift
nonisolated init(_ data: Data) where ID == Data.Element.ID, Content == TableRow<Data.Element>, Data.Element : Identifiable
```

## Parameters

- **data**: The identified data that the [ForEach](../ForEach.zh-Hans.md) instance uses to create table rows dynamically.

## Discussion

The following example creates a `Person` type that conforms to [doc://com.apple.documentation/documentation/Swift/Identifiable], and an array of this type called `people`. A `ForEach` instance iterates over the array, producing new [TableRow](../TableRow.zh-Hans.md) instances implicitly.

```swift
private struct Person: Identifiable {
    var id = UUID()
    var name: String
}

@State private var people: [Person] = /* ... */

Table(of: Person.self) {
    TableColumn("ID", value: \.id.uuidString)
    TableColumn("Name", value: \.name)
} rows: {
    Section("Team") {
        /* This is equivalent to the line below:
        ForEach(people) { TableRow($0) }
        */
        ForEach(people)
    }
}
```

## Creating a collection

- **init(_:content:)**: Creates an instance that uniquely identifies and creates map content across updates based on the identity of the underlying data.
- **init(_:id:content:)**: Creates an instance that uniquely identifies and creates map content across updates based on the provided key path to the underlying data’s identifier.

