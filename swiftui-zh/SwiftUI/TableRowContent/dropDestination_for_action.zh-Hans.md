--- 来源：https://developer.apple.com/documentation/SwiftUI/TableRowContent/dropDestination(for:action:)

抓取时间：2025-12-01T11:30:30Z

---

# dropDestination(for:action:)

**实例方法**

将整行定义为拖放操作的目标位置，并使用您指定的闭包处理拖放的内容。

## 声明

```swift
@MainActor @preconcurrency func dropDestination<T>(for payloadType: T.Type = T.self, action: @escaping ([T]) -> Void) -> some TableRowContent<Self.TableRowValue> where T : Transferable

```

## 参数

- **payloadType**：拖放模型的预期类型。

- **action**：一个闭包，接收拖放的内容，如果拖放操作成功，则返回 `true`；否则，返回 `false`。

## 返回值

返回一个指定类型的拖放操作的目标行。

## 交互管理

- **draggable(_:)**：激活此行作为拖放操作的源。

- **onHover(perform:)**：添加一个操作，当指针移动到整行或离开整行时执行该操作。

- **itemProvider(_:)**：提供一个闭包，用于提供特定数据元素的拖放表示。

- **ItemProviderTableRowModifier**：一个表格行修饰符，用于将项目提供程序与某些基本行内容关联起来。


---
source: https://developer.apple.com/documentation/SwiftUI/TableRowContent/dropDestination(for:action:)
crawled: 2025-12-01T11:30:30Z
---

# dropDestination(for:action:)

**Instance Method**

Defines the entire row as a destination of a drag and drop operation that handles the dropped content with a closure that you specify.

## Declaration

```swift
@MainActor @preconcurrency func dropDestination<T>(for payloadType: T.Type = T.self, action: @escaping ([T]) -> Void) -> some TableRowContent<Self.TableRowValue> where T : Transferable

```

## Parameters

- **payloadType**: The expected type of the dropped models.
- **action**: A closure that takes the dropped content and responds with `true` if the drop operation was successful; otherwise, return `false`.

## Return Value

A row that provides a drop destination for a drag operation of the specified type.

## Managing interaction

- **draggable(_:)**: Activates this row as the source of a drag and drop operation.
- **onHover(perform:)**: Adds an action to perform when the pointer moves onto or away from the entire row.
- **itemProvider(_:)**: Provides a closure that vends the drag representation for a particular data element.
- **ItemProviderTableRowModifier**: A table row modifier that associates an item provider with some base row content.

