--- 来源：https://developer.apple.com/documentation/swiftui/dropproposal

抓取时间：2025-12-04T13:39:13Z

---

# DropProposal

**Structure**

Drop 操作的行为。

## 声明

```swift
struct DropProposal
```

## 创建 Drop 操作

- **init(operation:)**

- **operation**：Drop 操作提议执行的操作。

## 初始化器

- **init(withinApplication:outsideApplication:)**

## 实例属性

- **operationOutsideApplication**：源应用程序外部 Drop 操作的属性。

## 使用项目提供程序移动项目

- **itemProvider(_:)**：提供一个闭包，用于提供特定数据元素的拖放表示形式。

- **onDrag(_:preview:)**：激活此视图作为拖放操作的源。

- **onDrag(_:)**：激活此视图作为拖放操作的源。

- **onDrop(of:isTargeted:perform:)**：定义拖放操作的目标位置，该位置使用您指定的闭包处理拖放的内容。

- **onDrop(of:delegate:)**：定义拖放操作的目标位置，该目标位置的行为由您提供的委托控制。

- **DropDelegate**：您实现的接口，用于与已修改为接受拖放操作的视图中的拖放操作进行交互。

- **DropOperation**：操作类型，用于确定用户放下拖放项时拖放会话的解析方式。

- **DropInfo**：拖放的当前状态。

## 符合以下规范

- Copyable

- CustomDebugStringConvertible

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/swiftui/dropproposal
crawled: 2025-12-04T13:39:13Z
---

# DropProposal

**Structure**

The behavior of a drop.

## Declaration

```swift
struct DropProposal
```

## Creating a drop proposal

- **init(operation:)**
- **operation**: The drop operation that the drop proposes to perform.

## Initializers

- **init(withinApplication:outsideApplication:)**

## Instance Properties

- **operationOutsideApplication**: The drop operation for drops outside the source application.

## Moving items using item providers

- **itemProvider(_:)**: Provides a closure that vends the drag representation to be used for a particular data element.
- **onDrag(_:preview:)**: Activates this view as the source of a drag and drop operation.
- **onDrag(_:)**: Activates this view as the source of a drag and drop operation.
- **onDrop(of:isTargeted:perform:)**: Defines the destination of a drag-and-drop operation that handles the dropped content with a closure that you specify.
- **onDrop(of:delegate:)**: Defines the destination of a drag and drop operation using behavior controlled by the delegate that you provide.
- **DropDelegate**: An interface that you implement to interact with a drop operation in a view modified to accept drops.
- **DropOperation**: Operation types that determine how a drag and drop session resolves when the user drops a drag item.
- **DropInfo**: The current state of a drop.

## Conforms To

- Copyable
- CustomDebugStringConvertible
- Sendable
- SendableMetatype

