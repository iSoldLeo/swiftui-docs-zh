--- 来源：https://developer.apple.com/documentation/SwiftUI/TableRowContent/draggable(_:)

抓取时间：2025-12-01T11:30:29Z

---

# draggable(_:)

**实例方法**

激活此行作为拖放操作的源。

## 声明

```swift
@MainActor @preconcurrency func draggable<T>(_ payload: @autoclosure @escaping () -> T) -> some TableRowContent<Self.TableRowValue> where T : Transferable

```

## 参数

- **payload**：一个闭包，返回一个符合 [doc://com.apple.documentation/documentation/CoreTransferable/Transferable] 的实例或值，表示此视图中的可拖动数据。

## 返回值

一个激活此行作为拖放操作源的行。

## 说明

应用 `draggable(_:)` 修饰符会为该行添加相应的拖放手势。

## 管理交互

- **dropDestination(for:action:)**：将整行定义为拖放操作的目标区域，并使用您指定的闭包处理拖放的内容。

- **onHover(perform:)**：添加指针移动到整行或离开整行时要执行的操作。

- **itemProvider(_:)**：提供一个闭包，用于提供特定数据元素的拖放表示。

- **ItemProviderTableRowModifier**：一个表格行修饰符，用于将项目提供程序与某些基本行内容关联起来。


---
source: https://developer.apple.com/documentation/SwiftUI/TableRowContent/draggable(_:)
crawled: 2025-12-01T11:30:29Z
---

# draggable(_:)

**Instance Method**

Activates this row as the source of a drag and drop operation.

## Declaration

```swift
@MainActor @preconcurrency func draggable<T>(_ payload: @autoclosure @escaping () -> T) -> some TableRowContent<Self.TableRowValue> where T : Transferable

```

## Parameters

- **payload**: A closure that returns a single instance or a value conforming to [doc://com.apple.documentation/documentation/CoreTransferable/Transferable] that represents the draggable data from this view.

## Return Value

A row that activates this row as the source of a drag and drop operation.

## Discussion

Applying the `draggable(_:)` modifier adds the appropriate gestures for drag and drop to this row.

## Managing interaction

- **dropDestination(for:action:)**: Defines the entire row as a destination of a drag and drop operation that handles the dropped content with a closure that you specify.
- **onHover(perform:)**: Adds an action to perform when the pointer moves onto or away from the entire row.
- **itemProvider(_:)**: Provides a closure that vends the drag representation for a particular data element.
- **ItemProviderTableRowModifier**: A table row modifier that associates an item provider with some base row content.

