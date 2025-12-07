--- 来源：https://developer.apple.com/documentation/SwiftUI/View/dragContainer(for:itemID:in:_:)

抓取时间：2025-11-30T21:08:39Z

---

# dragContainer(for:itemID:in:_:)

**实例方法**

一个包含可拖动视图的容器。

## 声明

```swift
nonisolated func dragContainer<ItemID, Item, Data>(for itemType: Item.Type = Item.self, itemID: KeyPath<Item, ItemID>, in namespace: Namespace.ID? = nil, _ payload: @escaping (Array<ItemID>) -> Data) -> some View where ItemID : Hashable, ItemID : Sendable, Item : Transferable, Item == Data.Element, Data : Collection

```

## 参数

- **itemType**：被拖动项的类型。

- **itemID**：提供项标识符的闭包。

- **namespace**：标识拖动容器的命名空间。

- **payload**：在拖动操作开始时调用的闭包。作为参数，闭包接收所有选定项的标识符（如果拖动项是选定项的一部分），或者仅接收拖动项的标识符（如果拖动项不是选定项的一部分）。使用传递的标识符，构建要拖动的有效负载，并从闭包返回。返回空的 `Collection` 以禁用拖动。

## 返回值

一个可作为拖放操作源的视图，从用户手势输入开始。

## 说明

在下面的示例中，应用程序呈现一个具有 `Fruit` 值的视图。`Fruit` 不符合 `Identifiable` 的要求，但使用其名称作为标识符。

```swift
   @State private var fruits: [Fruit]
   @State private var selection: [String]

   var body: some View {
       VStack {
           ForEach(fruits) { fruit in
               FruitView(fruit)
                   .draggable(containerItemID: fruit.name)
           }
       }
       .dragContainer(itemID: \Fruit.name) { ids in
          fruits(with: ids)
       }
   }

   func fruits(with ids: [String]) -> [Fruit] { ... }

   struct Fruit: Transferable {
       var name: String
       ...
   }
```


---
source: https://developer.apple.com/documentation/SwiftUI/View/dragContainer(for:itemID:in:_:)
crawled: 2025-11-30T21:08:39Z
---

# dragContainer(for:itemID:in:_:)

**Instance Method**

A container with draggable views.

## Declaration

```swift
nonisolated func dragContainer<ItemID, Item, Data>(for itemType: Item.Type = Item.self, itemID: KeyPath<Item, ItemID>, in namespace: Namespace.ID? = nil, _ payload: @escaping (Array<ItemID>) -> Data) -> some View where ItemID : Hashable, ItemID : Sendable, Item : Transferable, Item == Data.Element, Data : Collection

```

## Parameters

- **itemType**: A type of the dragged items.
- **itemID**: A closure that provides an item’s identifier.
- **namespace**: A namespace that identifies the drag container.
- **payload**: A closure which is called when a drag operation begins. As an argument, the closure receives either the identifiers of all the selected items, if the dragged item is a part of selection or only the identifier of the dragged item, if it is not part of the selection. Using the passed identifiers, put together the payload to drag, and return from the closure. Return an empty `Collection` to disable the drag.

## Return Value

A view that can be activated as the source of a drag and drop operation, beginning with user gesture input.

## Discussion

In an example below, an app presents a view with `Fruit` values. `Fruit` does not conform to `Identifiable` but uses its name as its identifier.

```swift
   @State private var fruits: [Fruit]
   @State private var selection: [String]

   var body: some View {
       VStack {
           ForEach(fruits) { fruit in
               FruitView(fruit)
                   .draggable(containerItemID: fruit.name)
           }
       }
       .dragContainer(itemID: \Fruit.name) { ids in
          fruits(with: ids)
       }
   }

   func fruits(with ids: [String]) -> [Fruit] { ... }

   struct Fruit: Transferable {
       var name: String
       ...
   }
```

