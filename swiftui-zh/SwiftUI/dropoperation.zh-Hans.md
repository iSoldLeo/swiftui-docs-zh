--- 来源：https://developer.apple.com/documentation/swiftui/dropoperation
抓取时间：2025-12-04T13:39:14Z

---

# DropOperation

**Enumeration**

操作类型决定了用户拖放项目时拖放会话的最终处理方式。

## 声明

```swift
enum DropOperation
```

## 获取操作类型

- **DropOperation.cancel**：取消拖放操作，不传输任何数据。

- **DropOperation.copy**：将数据复制到修改后的视图。

- **DropOperation.forbidden**：当前位置不允许执行拖放操作。

- **DropOperation.move**：移动拖放项目所代表的数据，而不是复制它。

## 结构

- **DropOperation.Set**：一组拖放操作，对应于 `DropOperation` 中的匹配情况。

## 枚举情况

- **DropOperation.alias**

- **DropOperation.delete**：删除数据。该项被拖放到回收站或其他语义上表示删除的目标位置。

## 使用项提供程序移动项

- **itemProvider(_:)**：提供一个闭包，用于提供特定数据元素的拖放表示。

- **onDrag(_:preview:)**：激活此视图作为拖放操作的源。

- **onDrag(_:)**：激活此视图作为拖放操作的源。

- **onDrop(of:isTargeted:perform:)**：定义拖放操作的目标位置，该位置使用您指定的闭包处理拖放的内容。

- **onDrop(of:delegate:)**：定义拖放操作的目标位置，该位置使用您提供的委托控制的行为。

- **DropDelegate**：您实现的接口，用于与已修改为接受拖放操作的视图中的拖放操作进行交互。

- **DropProposal**：拖放操作的行为。

- **DropInfo**：拖放操作的当前状态。

## 符合以下协议：

- Copyable

- Equatable

- Hashable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/swiftui/dropoperation
crawled: 2025-12-04T13:39:14Z
---

# DropOperation

**Enumeration**

Operation types that determine how a drag and drop session resolves when the user drops a drag item.

## Declaration

```swift
enum DropOperation
```

## Getting operation types

- **DropOperation.cancel**: Cancel the drag operation and transfer no data.
- **DropOperation.copy**: Copy the data to the modified view.
- **DropOperation.forbidden**: The drop activity is not allowed at this time or location.
- **DropOperation.move**: Move the data represented by the drag items instead of copying it.

## Structures

- **DropOperation.Set**: A set of drop operations, corresponding to matching cases in `DropOperation`.

## Enumeration Cases

- **DropOperation.alias**
- **DropOperation.delete**: Delete the data. The item was dragged to Trash or to another destination that semantically represents deletion.

## Moving items using item providers

- **itemProvider(_:)**: Provides a closure that vends the drag representation to be used for a particular data element.
- **onDrag(_:preview:)**: Activates this view as the source of a drag and drop operation.
- **onDrag(_:)**: Activates this view as the source of a drag and drop operation.
- **onDrop(of:isTargeted:perform:)**: Defines the destination of a drag-and-drop operation that handles the dropped content with a closure that you specify.
- **onDrop(of:delegate:)**: Defines the destination of a drag and drop operation using behavior controlled by the delegate that you provide.
- **DropDelegate**: An interface that you implement to interact with a drop operation in a view modified to accept drops.
- **DropProposal**: The behavior of a drop.
- **DropInfo**: The current state of a drop.

## Conforms To

- Copyable
- Equatable
- Hashable
- Sendable
- SendableMetatype

