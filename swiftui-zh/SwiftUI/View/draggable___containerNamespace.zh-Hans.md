--- 来源：https://developer.apple.com/documentation/SwiftUI/View/draggable(_:containerNamespace:_:)

抓取时间：2025-11-30T21:08:41Z

---

# draggable(_:containerNamespace:_:)

**实例方法**

激活此视图作为拖放操作的源，允许提供可选的可识别有效负载，并指定此视图所属的拖放容器的命名空间。

## 声明

```swift
nonisolated func draggable<Item>(_ itemType: Item.Type = Item.self, containerNamespace: Namespace.ID? = nil, _ item: @escaping () -> Item?) -> some View where Item : Transferable, Item : Identifiable, Item.ID : Sendable

```

## 参数

- **itemType**：被拖放项的类型。

- **containerNamespace**：关联的拖放容器的命名空间。

## 返回值

一个视图，该视图激活此视图作为拖放操作的源，从用户手势输入开始。

## 讨论

应用 `draggable(_:containerNamespace_:)` 修饰符会为该视图添加相应的拖放手势。

```swift
   var fruits: [Fruit]

   var body: some View {
       ScrollView {
           VStack {
               ForEach(fruits) { fruit in
                   FruitView(fruit)
                       .draggable(fruit)
               }
           }
       }
   }

   struct Fruit: Identifiable, Transferable { ... }
```

如果可拖动视图位于容器内，则会参与容器的拖放会话：

```swift
   var fruits: [Fruit]
   var selectedFruits: [Fruit.ID]

   var body: some View {
       ScrollView {
           VStack {
               ForEach(fruits) { fruit in
                   FruitView(fruit)
                       .draggable(fruit)
               }
           }
       }
       .dragContainer(for: Fruit.self) { identifiers in
           fruits(with: identifiers)
       }
       .dragContainerSelection(selectedFruits)
   }

   func fruits(with: [Fruit.ID]) -> [Fruit] { ... }
   struct Fruit: Identifiable, Transferable { ... }
```

拖动操作开始时，会生成该视图的渲染图并将其用作预览图像。


---
source: https://developer.apple.com/documentation/SwiftUI/View/draggable(_:containerNamespace:_:)
crawled: 2025-11-30T21:08:41Z
---

# draggable(_:containerNamespace:_:)

**Instance Method**

Activates this view as the source of a drag and drop operation, allowing to provide optional identifiable payload and specify the namespace of the drag container this view belongs to.

## Declaration

```swift
nonisolated func draggable<Item>(_ itemType: Item.Type = Item.self, containerNamespace: Namespace.ID? = nil, _ item: @escaping () -> Item?) -> some View where Item : Transferable, Item : Identifiable, Item.ID : Sendable

```

## Parameters

- **itemType**: A type of the dragged item.
- **containerNamespace**: A namespace of the associated drag container.

## Return Value

A view that activates this view as the source of a drag and drop operation, beginning with user gesture input.

## Discussion

Applying the `draggable(_:containerNamespace_:)` modifier adds the appropriate gestures for drag and drop to this view.

```swift
   var fruits: [Fruit]

   var body: some View {
       ScrollView {
           VStack {
               ForEach(fruits) { fruit in
                   FruitView(fruit)
                       .draggable(fruit)
               }
           }
       }
   }

   struct Fruit: Identifiable, Transferable { ... }
```

If the draggable view is enclosed in a container, it participates in container drag-and-drop sessions:

```swift
   var fruits: [Fruit]
   var selectedFruits: [Fruit.ID]

   var body: some View {
       ScrollView {
           VStack {
               ForEach(fruits) { fruit in
                   FruitView(fruit)
                       .draggable(fruit)
               }
           }
       }
       .dragContainer(for: Fruit.self) { identifiers in
           fruits(with: identifiers)
       }
       .dragContainerSelection(selectedFruits)
   }

   func fruits(with: [Fruit.ID]) -> [Fruit] { ... }
   struct Fruit: Identifiable, Transferable { ... }
```

When a drag operation begins, a rendering of this view is generated and used as the preview image.

