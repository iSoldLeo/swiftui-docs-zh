--- 来源：https://developer.apple.com/documentation/swiftui/itemprovidertablerowmodifier
抓取时间：2025-12-05T22:29:01Z

---

# ItemProviderTableRowModifier

**Structure**

一个表格行修饰符，用于将项目提供程序与某些基本行内容关联起来。

## 声明

```swift
@MainActor @preconcurrency struct ItemProviderTableRowModifier
```

## 实例属性

- **body**

## 类型别名

- **ItemProviderTableRowModifier.Body**

## 管理交互

- **draggable(_:)**：激活此行作为拖放操作的源。

- **dropDestination(for:action:)**：将整行定义为拖放操作的目标区域，并使用您指定的闭包处理拖放的内容。

- **onHover(perform:)**：添加一个操作，当指针移动到整行上或离开整行时执行该操作。

- **itemProvider(_:)**：提供一个闭包，用于提供特定数据元素的拖放表示。


---
source: https://developer.apple.com/documentation/swiftui/itemprovidertablerowmodifier
crawled: 2025-12-05T22:29:01Z
---

# ItemProviderTableRowModifier

**Structure**

A table row modifier that associates an item provider with some base row content.

## Declaration

```swift
@MainActor @preconcurrency struct ItemProviderTableRowModifier
```

## Instance Properties

- **body**

## Type Aliases

- **ItemProviderTableRowModifier.Body**

## Managing interaction

- **draggable(_:)**: Activates this row as the source of a drag and drop operation.
- **dropDestination(for:action:)**: Defines the entire row as a destination of a drag and drop operation that handles the dropped content with a closure that you specify.
- **onHover(perform:)**: Adds an action to perform when the pointer moves onto or away from the entire row.
- **itemProvider(_:)**: Provides a closure that vends the drag representation for a particular data element.

