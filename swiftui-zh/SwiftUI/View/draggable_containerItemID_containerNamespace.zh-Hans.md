--- 来源：https://developer.apple.com/documentation/SwiftUI/View/draggable(containerItemID:containerNamespace:)

抓取时间：2025-11-30T21:08:45Z

---

# draggable(containerItemID:containerNamespace:)

**实例方法**

在拖放容器内，激活此视图作为拖放操作的源。支持惰性拖放容器。

## 声明

```swift
nonisolated func draggable<ItemID>(containerItemID: ItemID, containerNamespace: Namespace.ID? = nil) -> some View where ItemID : Hashable, ItemID : Sendable

```

## 参数

- **containerItemID**：关联的拖放有效负载的标识符。

- **containerNamespace**：关联的拖放容器的命名空间。

## 返回值

一个视图，该视图激活此视图作为拖放操作的源，从用户手势输入开始。

## 讨论

此修饰符将视图标记为包含它的 `dragContainer(_:containerNamespace:_:)` 的可拖动元素。由于此修饰符不需要提供有效负载，只需要提供其标识符，因此它是惰性工作的（框架仅在拖动开始时请求提供实际拖动的项；此外，框架无需渲染视图即可访问其有效负载）。

将 `draggable(containerItemID:containerNamespace:)` 修饰符应用于拖动容器内的视图，会为该视图添加相应的拖放手势。SwiftUI 会为拖动生成默认的拖动预览。

下面，每个 `FruitView` 都被分配了一个标识符：它所代表的水果的代码。拖动开始时，会调用 `dragContainer` 闭包，并传入所选水果的代码；或者，如果用户拖动的视图未被选中，则闭包会接收该视图的标识符作为参数。

```swift
   var fruits: [Fruit]
   var selectedFruitCodes: [UUID]

   var body: some View {
       VStack {
           ForEach(fruits) { fruit in
               .draggable(containerItemID: fruit.code)
       }
       .dragContainer { codes in
           fruits(with: codes)
       }
       .dragContainerSelection(selectedFruitCodes)
   }

   func fruits(with codes: [UUID]) -> [Fruit] { ... }

   struct Fruit: Transferable {
       var code: UUID
       ...
   }
```


---
source: https://developer.apple.com/documentation/SwiftUI/View/draggable(containerItemID:containerNamespace:)
crawled: 2025-11-30T21:08:45Z
---

# draggable(containerItemID:containerNamespace:)

**Instance Method**

Inside a drag container, activates this view as the source of a drag and drop operation. Supports lazy drag containers.

## Declaration

```swift
nonisolated func draggable<ItemID>(containerItemID: ItemID, containerNamespace: Namespace.ID? = nil) -> some View where ItemID : Hashable, ItemID : Sendable

```

## Parameters

- **containerItemID**: An identifier of the associated drag payload.
- **containerNamespace**: A namespace of the associated drag container.

## Return Value

A view that activates this view as the source of a drag and drop operation, beginning with user gesture input.

## Discussion

This modifier marks the view as a draggable element of an enclosing `dragContainer(_:containerNamespace:_:)`. Since this modifier does not require to provide the payload, only its identifier, it works lazily (the framework asks to provide the actual dragged items only when drag starts; also, the framework doesn’t have to render a view in order to access its payload).

Applying the `draggable(containerItemID:containerNamespace:)` modifier to a view inside a drag container adds the appropriate gestures for drag and drop to this view. SwiftUI generates a default drag preview for drag.

Below, each `FruitView` is assigned an identifier: a code of a fruit it represents. When dragging begins, the `dragContainer` closure is called with the codes of the selected fruit, or, if a user drags a view that is not selected, the closure receives the identifier of that view as a parameter.

```swift
   var fruits: [Fruit]
   var selectedFruitCodes: [UUID]

   var body: some View {
       VStack {
           ForEach(fruits) { fruit in
               .draggable(containerItemID: fruit.code)
       }
       .dragContainer { codes in
           fruits(with: codes)
       }
       .dragContainerSelection(selectedFruitCodes)
   }

   func fruits(with codes: [UUID]) -> [Fruit] { ... }

   struct Fruit: Transferable {
       var code: UUID
       ...
   }
```

