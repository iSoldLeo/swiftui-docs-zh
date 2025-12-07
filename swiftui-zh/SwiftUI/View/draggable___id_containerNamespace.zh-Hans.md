--- 来源：https://developer.apple.com/documentation/SwiftUI/View/draggable(_:id:containerNamespace:_:)

抓取时间：2025-12-02T17:23:40Z

---

# draggable(_:id:containerNamespace:_:)

**实例方法**

激活此视图作为拖放操作的源，允许提供可选的有效负载并指定此视图所属的拖放容器的命名空间。

## 声明

```swift
nonisolated func draggable<Item, ItemID>(_ itemType: Item.Type = Item.self, id: KeyPath<Item, ItemID>, containerNamespace: Namespace.ID? = nil, _ payload: @escaping () -> Item?) -> some View where Item : Transferable, ItemID : Hashable, ItemID : Sendable

```

## 参数

- **itemType**：被拖放项的类型。

- **id**：项标识符的键路径。

- **containerNamespace**：关联的拖放容器的命名空间。

- **payload**：返回一个闭包，该闭包返回一个符合 [doc://com.apple.documentation/documentation/CoreTransferable/Transferable] 的单个实例或值，表示此视图中的可拖动数据。

## 返回值

激活此视图作为拖放操作的源，该操作从用户手势输入开始。

## 说明

应用 `draggable(_:id:containerNamespace:_:)` 修饰符会将相应的拖放手势添加到此视图。拖动操作开始时，会生成此视图的渲染结果并将其用作预览图像。

```swift
   var fruits: [Fruit]

   var body: some View {
       ScrollView {
           VStack {
               ForEach(fruits) { fruit in
                   FruitView(fruit)
                       .draggable(Fruit.self, id: \.dragID) {
                           fruit.supportsDrag ? fruit : nil
                       }
               }
           }
       }
   }

   struct Fruit: Transferable {
       var supportsDrag: Bool
       var dragID: UUID
   }
```

如果可拖动视图包含在容器中，它将参与容器的拖放会话：

```swift
   var fruits: [Fruit]
   var selectedFruits: [UUID]

   var body: some View {
       ScrollView {
           VStack {
               ForEach(fruits) { fruit in
                   FruitView(fruit)
                       .draggable(Fruit.self, id: \.dragID) {
                           fruit.supportsDrag ? fruit : nil
                       }
               }
           }
       }
       .dragContainer(for: Fruit.self) { identifiers in
           fruits(with: identifiers)
       }
       .dragContainerSelection(selectedFruits)
   }

   func fruits(with: [UUID]) -> [Fruit] { ... }
```


---
source: https://developer.apple.com/documentation/SwiftUI/View/draggable(_:id:containerNamespace:_:)
crawled: 2025-12-02T17:23:40Z
---

# draggable(_:id:containerNamespace:_:)

**Instance Method**

Activates this view as the source of a drag and drop operation, allowing to provide optional payload and specify the namespace of the drag container this view belongs to.

## Declaration

```swift
nonisolated func draggable<Item, ItemID>(_ itemType: Item.Type = Item.self, id: KeyPath<Item, ItemID>, containerNamespace: Namespace.ID? = nil, _ payload: @escaping () -> Item?) -> some View where Item : Transferable, ItemID : Hashable, ItemID : Sendable

```

## Parameters

- **itemType**: A type of the dragged item.
- **id**: An key path of the identifier of an item.
- **containerNamespace**: A namespace of the associated drag container.
- **payload**: A closure that returns a single instance or a value conforming to [doc://com.apple.documentation/documentation/CoreTransferable/Transferable] that represents the draggable data from this view.

## Return Value

A view that activates this view as the source of a drag and drop operation, beginning with user gesture input.

## Discussion

Applying the `draggable(_:id:containerNamespace:_:)` modifier adds the appropriate gestures for drag and drop to this view. When a drag operation begins, a rendering of this view is generated and used as the preview image.

```swift
   var fruits: [Fruit]

   var body: some View {
       ScrollView {
           VStack {
               ForEach(fruits) { fruit in
                   FruitView(fruit)
                       .draggable(Fruit.self, id: \.dragID) {
                           fruit.supportsDrag ? fruit : nil
                       }
               }
           }
       }
   }

   struct Fruit: Transferable {
       var supportsDrag: Bool
       var dragID: UUID
   }
```

If the draggable view is enclosed in a container, it participates in container drag-and-drop sessions:

```swift
   var fruits: [Fruit]
   var selectedFruits: [UUID]

   var body: some View {
       ScrollView {
           VStack {
               ForEach(fruits) { fruit in
                   FruitView(fruit)
                       .draggable(Fruit.self, id: \.dragID) {
                           fruit.supportsDrag ? fruit : nil
                       }
               }
           }
       }
       .dragContainer(for: Fruit.self) { identifiers in
           fruits(with: identifiers)
       }
       .dragContainerSelection(selectedFruits)
   }

   func fruits(with: [UUID]) -> [Fruit] { ... }
```

