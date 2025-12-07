--- 来源：https://developer.apple.com/documentation/SwiftUI/TableRowContent/onHover(perform:)

抓取时间：2025-12-03T06:41:12Z

---

# onHover(perform:)

**实例方法**

添加一个当指针移动到整行上或离开整行时要执行的操作。

## 声明

```swift
@MainActor @preconcurrency func onHover(perform action: @escaping (Bool) -> Void) -> some TableRowContent<Self.TableRowValue>

```

## 管理交互

- **draggable(_:)**：激活此行作为拖放操作的源。

- **dropDestination(for:action:)**：将整行定义为拖放操作的目标，并使用您指定的闭包处理拖放的内容。

- **itemProvider(_:)**：提供一个闭包，用于提供特定数据元素的拖放表示。

- **ItemProviderTableRowModifier**：一种表格行修饰符，用于将物品提供者与某些基础行内容关联起来。


---
source: https://developer.apple.com/documentation/SwiftUI/TableRowContent/onHover(perform:)
crawled: 2025-12-03T06:41:12Z
---

# onHover(perform:)

**Instance Method**

Adds an action to perform when the pointer moves onto or away from the entire row.

## Declaration

```swift
@MainActor @preconcurrency func onHover(perform action: @escaping (Bool) -> Void) -> some TableRowContent<Self.TableRowValue>

```

## Managing interaction

- **draggable(_:)**: Activates this row as the source of a drag and drop operation.
- **dropDestination(for:action:)**: Defines the entire row as a destination of a drag and drop operation that handles the dropped content with a closure that you specify.
- **itemProvider(_:)**: Provides a closure that vends the drag representation for a particular data element.
- **ItemProviderTableRowModifier**: A table row modifier that associates an item provider with some base row content.

