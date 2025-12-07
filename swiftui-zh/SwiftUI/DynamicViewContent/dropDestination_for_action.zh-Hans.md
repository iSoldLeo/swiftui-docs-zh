--- 来源：https://developer.apple.com/documentation/SwiftUI/DynamicViewContent/dropDestination(for:action:)

抓取时间：2025-12-03T05:37:30Z

---

# dropDestination(for:action:)

**实例方法**

设置动态视图的插入操作。

## 声明

```swift
nonisolated func dropDestination<T>(for payloadType: T.Type = T.self, action: @escaping ([T], Int) -> Void) -> some DynamicViewContent where T : Transferable

```

## 参数

- **payloadType**：要拖放的模型类型。

- **action**：SwiftUI 在向视图添加元素时调用的闭包。该闭包接受两个参数：第一个参数是相对于动态视图底层数据集合的偏移量。第二个参数是一个 `Transferable` 项数组，表示要插入的数据。

## 返回值

当元素插入到原始视图中时，会调用 `action` 的视图。

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
    List {
        ForEach(profiles) { profile in
            Text(profile.givenName)
        }
        .dropDestination(for: Profile.self) { receivedProfiles, offset in
            profiles.insert(contentsOf: receivedProfiles, at: offset)
        }
    }
}
```

## 响应更新

- **onDelete(perform:)**：设置动态视图的删除操作。您必须删除 `action` 中的相应项，因为该操作会在行已从 [List](../List.zh-Hans.md) 中移除后调用。

- **onInsert(of:perform:)**：设置动态视图的插入操作。

- **onMove(perform:)**：设置动态视图的移动操作。


---
source: https://developer.apple.com/documentation/SwiftUI/DynamicViewContent/dropDestination(for:action:)
crawled: 2025-12-03T05:37:30Z
---

# dropDestination(for:action:)

**Instance Method**

Sets the insert action for the dynamic view.

## Declaration

```swift
nonisolated func dropDestination<T>(for payloadType: T.Type = T.self, action: @escaping ([T], Int) -> Void) -> some DynamicViewContent where T : Transferable

```

## Parameters

- **payloadType**: Type of the models that are dropped.
- **action**: A closure that SwiftUI invokes when elements are added to the view. The closure takes two arguments: The first argument is the offset relative to the dynamic view’s underlying collection of data. The second argument is an array of `Transferable` items that represents the data that you want to insert.

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
    List {
        ForEach(profiles) { profile in
            Text(profile.givenName)
        }
        .dropDestination(for: Profile.self) { receivedProfiles, offset in
            profiles.insert(contentsOf: receivedProfiles, at: offset)
        }
    }
}
```

## Responding to updates

- **onDelete(perform:)**: Sets the deletion action for the dynamic view. You must delete the corresponding item within `action`, as it will be called after the row has already been removed from the [List](../List.zh-Hans.md).
- **onInsert(of:perform:)**: Sets the insert action for the dynamic view.
- **onMove(perform:)**: Sets the move action for the dynamic view.

