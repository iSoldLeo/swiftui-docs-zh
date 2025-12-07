--- 来源：https://developer.apple.com/documentation/SwiftUI/View/draggable(_:item:containerNamespace:)

抓取时间：2025-11-30T21:08:44Z

---

# draggable(_:item:containerNamespace:)

**实例方法**

激活此视图作为拖放操作的源，允许提供可选的可识别有效负载，并指定此视图所属的拖放容器的命名空间。

## 声明

```swift
nonisolated func draggable<Item>(_ itemType: Item.Type = Item.self, item: @autoclosure @escaping () -> Item?, containerNamespace: Namespace.ID? = nil) -> some View where Item : Transferable, Item : Identifiable, Item.ID : Sendable

```

## 参数

- **itemType**：被拖放项的类型。

- **containerNamespace**：关联的拖放容器的命名空间。

## 返回值

一个视图，该视图激活此视图作为拖放操作的源，从用户手势输入开始。

## 讨论

应用 `draggable(_:_:containerNamespace:)` 修饰符会为该视图添加拖放手势。当开始拖拽操作时，会生成该视图的渲染图并将其用作预览图像。

如果视图包含在 `dragContainer(for:in:_)` 中，则该视图会成为其可拖拽元素，并且该元素的标识符将用作拖拽有效载荷的标识符。

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
   }

   func fruits(with: [Fruit.ID]) -> [Fruit] { ... }
   struct Fruit: Identifiable, Transferable { ... }
```


---
source: https://developer.apple.com/documentation/SwiftUI/View/draggable(_:item:containerNamespace:)
crawled: 2025-11-30T21:08:44Z
---

# draggable(_:item:containerNamespace:)

**Instance Method**

Activates this view as the source of a drag and drop operation, allowing to provide optional identifiable payload and specify the namespace of the drag container this view belongs to.

## Declaration

```swift
nonisolated func draggable<Item>(_ itemType: Item.Type = Item.self, item: @autoclosure @escaping () -> Item?, containerNamespace: Namespace.ID? = nil) -> some View where Item : Transferable, Item : Identifiable, Item.ID : Sendable

```

## Parameters

- **itemType**: A type of the dragged item.
- **containerNamespace**: A namespace of the associated drag container.

## Return Value

A view that activates this view as the source of a drag and drop operation, beginning with user gesture input.

## Discussion

Applying the `draggable(_:_:containerNamespace:)` modifier adds the appropriate gestures for drag and drop to this view. When a drag operation begins, a rendering of this view is generated and used as the preview image.

If the view is enclosed in a `dragContainer(for:in:_)`, the view becomes its draggable element, and the item’s identifier is used as drag payload identifier.

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
   }

   func fruits(with: [Fruit.ID]) -> [Fruit] { ... }
   struct Fruit: Identifiable, Transferable { ... }
```

