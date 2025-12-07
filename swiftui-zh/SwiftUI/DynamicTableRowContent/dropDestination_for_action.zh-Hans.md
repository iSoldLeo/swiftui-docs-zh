---
来源：https://developer.apple.com/documentation/SwiftUI/DynamicTableRowContent/dropDestination(for:action:)
抓取时间： 2025-12-01T11:30:45Z
---

# dropDestination(for:action:)

**实例方法**

设置动态表行的插入操作。

## 声明

```swift
func dropDestination<T>(for payloadType: T.Type = T.self, action: @escaping (Int, [T]) -> Void) -> ModifiedContent<Self, OnInsertTableRowModifier> where T : Transferable
```

## 参数

- **payloadType**：被删除的模型类型。
- **action**：当元素被添加到行集合时 SwiftUI 调用的闭包。闭包需要两个参数：第一个参数是相对于动态视图底层数据集合的偏移量。第二个参数是一个`Transferable` 项数组，表示要插入的数据。

## 返回值

当元素插入原始视图时，调用`action` 的视图。

## 讨论

```swift
struct Profile: Identifiable {
    let givenName: String
    let familyName: String
    let id = UUID()
}

@State private var profiles: [Profile] = [
    Person(givenName: "Juan", familyName: "Chavez"),
    Person(givenName: "Mei", familyName: "Chen"),
    Person(givenName: "Tom", familyName: "Clark"),
    Person(givenName: "Gita", familyName: "Kumar")
]

var body: some View {
    Table {
        TableColumn("Given Name", value: \.givenName)
        TableColumn("Family Name", value: \.familyName)
    } rows: {
        ForEach(profiles) {
            TableRow($0)
        }
        .dropDestination(
            for: Profile.self
        ) { offset, receivedProfiles in
            people.insert(contentsOf: receivedProfiles, at: offset)
        }
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/DynamicTableRowContent/dropDestination(for:action:)
crawled: 2025-12-01T11:30:45Z
---

# dropDestination(for:action:)

**Instance Method**

Sets the insert action for the dynamic table rows.

## Declaration

```swift
func dropDestination<T>(for payloadType: T.Type = T.self, action: @escaping (Int, [T]) -> Void) -> ModifiedContent<Self, OnInsertTableRowModifier> where T : Transferable
```

## Parameters

- **payloadType**: Type of the models that are dropped.
- **action**: A closure that SwiftUI invokes when elements are added to the collection of rows. The closure takes two arguments: The first argument is the offset relative to the dynamic view’s underlying collection of data. The second argument is an array of `Transferable` items that represents the data that you want to insert.

## Return Value

A view that calls `action` when elements are inserted into the original view.

## Discussion

```swift
struct Profile: Identifiable {
    let givenName: String
    let familyName: String
    let id = UUID()
}

@State private var profiles: [Profile] = [
    Person(givenName: "Juan", familyName: "Chavez"),
    Person(givenName: "Mei", familyName: "Chen"),
    Person(givenName: "Tom", familyName: "Clark"),
    Person(givenName: "Gita", familyName: "Kumar")
]

var body: some View {
    Table {
        TableColumn("Given Name", value: \.givenName)
        TableColumn("Family Name", value: \.familyName)
    } rows: {
        ForEach(profiles) {
            TableRow($0)
        }
        .dropDestination(
            for: Profile.self
        ) { offset, receivedProfiles in
            people.insert(contentsOf: receivedProfiles, at: offset)
        }
    }
}
```

