--- 来源：https://developer.apple.com/documentation/SwiftUI/View/dragContainer(for:in:_:)

抓取时间：2025-12-02T17:23:35Z

---

# dragContainer(for:in:_:)

**实例方法**

一个包含可拖动视图的容器，拖动有效负载基于多个被拖动项的标识符。

## 声明

```swift
nonisolated func dragContainer<Item, Data>(for itemType: Item.Type = Item.self, in namespace: Namespace.ID? = nil, _ payload: @escaping (Array<Item.ID>) -> Data) -> some View where Item : Transferable, Item : Identifiable, Item == Data.Element, Data : Collection, Item.ID : Sendable

```

## 参数

- **itemType**：被拖动项的类型。

- **namespace**：标识拖动容器的命名空间。

- **payload**：拖动操作开始时调用的闭包。作为参数，闭包接收所有已选项的标识符（如果拖动项是已选项的一部分）或仅接收拖动项的标识符（如果拖动项不是已选项的一部分）。使用传递的标识符，构建要拖动的有效负载，并从闭包返回。返回空的 `Collection` 以禁用拖动。

## 返回值

一个可作为拖放操作源的视图，从用户手势输入开始。

## 说明

使用 `dragContainerSelection(_:containerNamespace)` 修饰符将已选标识符列表提供给 SwiftUI。如果没有可用的选择信息，SwiftUI 会将拖动项的标识符传递给 `payload` 闭包。

在下面的示例中，应用程序呈现一个带有 `Fruit` 值的视图。当用户开始拖拽时，SwiftUI 会根据用户的选择来构建待拖拽物品的标识符列表。

```swift
   var fruits: [Fruit]
   @State private var selection: [Fruit.ID]

   var body: some View {
       VStack {
           ForEach(fruits) { fruit in
               FruitView(fruit)
                   .draggable(containerItemID: fruit.id)
           }
       }
       .dragContainer(for: Fruit.self) { ids in
          fruits(with: ids)
       }
       .dragContainerSelection(selection)
   }

   func fruits(with ids: [UUID]) -> [Fruit] { ... }

   struct Fruit: Transferable, Identifiable { ... }
```


---
source: https://developer.apple.com/documentation/SwiftUI/View/dragContainer(for:in:_:)
crawled: 2025-12-02T17:23:35Z
---

# dragContainer(for:in:_:)

**Instance Method**

A container with draggable views where the drag payload is based on multiple identifiers of dragged items.

## Declaration

```swift
nonisolated func dragContainer<Item, Data>(for itemType: Item.Type = Item.self, in namespace: Namespace.ID? = nil, _ payload: @escaping (Array<Item.ID>) -> Data) -> some View where Item : Transferable, Item : Identifiable, Item == Data.Element, Data : Collection, Item.ID : Sendable

```

## Parameters

- **itemType**: A type of the dragged items.
- **namespace**: A namespace that identifies the drag container.
- **payload**: A closure which is called when a drag operation begins. As an argument, the closure receives either the identifiers of all the selected items, if the dragged item is a part of selection or only the identifier of the dragged item, if it is not part of the selection. With the passed identifiers, put together the payload to drag, and return from the closure. Return an empty `Collection` to disable the drag.

## Return Value

A view that can be activated as the source of a drag and drop operation, beginning with user gesture input.

## Discussion

Provide the selected identifiers list to SwiftUI using `dragContainerSelection(_:containerNamespace)` modifier. In a case when there’s no selection information available, SwiftUI passes the dragged item identifier to the `payload` closure.

In an example below, an app presents a view with `Fruit` values. When a user starts drag, SwiftUI uses the selection to put together the list of item identifiers to drag.

```swift
   var fruits: [Fruit]
   @State private var selection: [Fruit.ID]

   var body: some View {
       VStack {
           ForEach(fruits) { fruit in
               FruitView(fruit)
                   .draggable(containerItemID: fruit.id)
           }
       }
       .dragContainer(for: Fruit.self) { ids in
          fruits(with: ids)
       }
       .dragContainerSelection(selection)
   }

   func fruits(with ids: [UUID]) -> [Fruit] { ... }

   struct Fruit: Transferable, Identifiable { ... }
```

