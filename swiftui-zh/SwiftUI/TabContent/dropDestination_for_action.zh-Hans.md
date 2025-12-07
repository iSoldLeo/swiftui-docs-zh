---
来源：https://developer.apple.com/documentation/SwiftUI/TabContent/dropDestination(for:action:)
抓取时间： 2025-12-01T10:50:49Z
---

# dropDestination(for:action:)

**实例方法**

定义拖放操作的目的地，该操作使用您指定的闭合器处理拖放的内容。

## 声明

```swift
@MainActor @preconcurrency func dropDestination<T>(for payloadType: T.Type = T.self, action: @escaping ([T]) -> Void) -> some TabContent<Self.TabValue> where T : Transferable

```

## 参数

- **payloadType**：被删除的模型类型。
- **action**：一个闭包，用于接收被丢弃的内容并作出适当响应。该闭包需要一个参数，即表示要插入的数据的可转移项数组。

## 返回值

一个视图，当元素被下放到标签页时调用`action`。

## 讨论

下拉内容可以是二进制数据、文件 URL 或文件承诺。

下拉目标是标签内容。

当用户将一个配置文件投放到一个组时，该示例会将该配置文件添加到该组。

```swift
struct Profile: Identifiable {
    let givenName: String
    let familyName: String
    let image = "person.fill"
    let id = UUID().uuidString
}

@State private var profiles = [
    Profile(givenName: "Juan", familyName: "Chavez"),
    Profile(givenName: "Mei", familyName: "Chen"),
    Profile(givenName: "Tom", familyName: "Clark"),
    Profile(givenName: "Gita", familyName: "Kumar")
]

@State private var favoriteProfiles: [Profile] = []

var body: some View {
    TabView {
        Tab("All Profiles", systemImage: "list.bullet") {
            List(profiles) { profile in
                Text(profile.givenName)
                    .draggable(profile.id)
            }
        }

        Tab("Favorites", systemImage: "star.fill") {
            ForEach(favoritedProfiles) { profile in
                Tab(profile.givenName, image: profile.image) {
                    Label(profile.givenName, systemImage: "star.fill")
                }
            }
        }
        .dropDestination(for: String.self) { receivedIds in
             // Add profiles with `receivedIds` to favorites
        }
   }
```


---
source: https://developer.apple.com/documentation/SwiftUI/TabContent/dropDestination(for:action:)
crawled: 2025-12-01T10:50:49Z
---

# dropDestination(for:action:)

**Instance Method**

Defines the destination of a drag and drop operation that handles the dropped content with a closure that you specify.

## Declaration

```swift
@MainActor @preconcurrency func dropDestination<T>(for payloadType: T.Type = T.self, action: @escaping ([T]) -> Void) -> some TabContent<Self.TabValue> where T : Transferable

```

## Parameters

- **payloadType**: Type of the models that are dropped.
- **action**: A closure that takes the dropped content and responds appropriately. The closure takes one argument, which is an array of Transferable items that represents the data to insert.

## Return Value

A view that calls `action` when elements are dropped onto the tab.

## Discussion

The dropped content can be provided as binary data, file URLs, or file promises.

The drop destination is the tab content.

This example adds a profile to a group when the user drops it onto onto that group.

```swift
struct Profile: Identifiable {
    let givenName: String
    let familyName: String
    let image = "person.fill"
    let id = UUID().uuidString
}

@State private var profiles = [
    Profile(givenName: "Juan", familyName: "Chavez"),
    Profile(givenName: "Mei", familyName: "Chen"),
    Profile(givenName: "Tom", familyName: "Clark"),
    Profile(givenName: "Gita", familyName: "Kumar")
]

@State private var favoriteProfiles: [Profile] = []

var body: some View {
    TabView {
        Tab("All Profiles", systemImage: "list.bullet") {
            List(profiles) { profile in
                Text(profile.givenName)
                    .draggable(profile.id)
            }
        }

        Tab("Favorites", systemImage: "star.fill") {
            ForEach(favoritedProfiles) { profile in
                Tab(profile.givenName, image: profile.image) {
                    Label(profile.givenName, systemImage: "star.fill")
                }
            }
        }
        .dropDestination(for: String.self) { receivedIds in
             // Add profiles with `receivedIds` to favorites
        }
   }
```

