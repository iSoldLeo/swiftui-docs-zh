---
来源： https://developer.apple.com/documentation/SwiftUI/DragConfiguration
抓取时间： 2025-12-02T17:42:38Z
---

# DragConfiguration

**Structure**

由拖动源提议的拖动行为。

## 声明

```swift
struct DragConfiguration
```

## 结构

- **DragConfiguration.OperationsOutsideApp**：描述建议拖动到其他应用程序的操作。
- **DragConfiguration.OperationsWithinApp**：描述建议拖动到应用程序内目的地的操作。

## 初始化程序

- **init(allowMove:)**：创建拖动配置，该配置除支持拖动复制外，还支持拖动移动。
- **init(allowMove:allowDelete:)**：创建的拖动配置除支持拖动到复制外，还支持拖动到移动和拖动到删除。
- **init(operationsWithinApp:operationsOutsideApp:)**：创建默认拖动配置，该配置支持在应用程序内拖动和拖动到其他应用程序的操作`.copy`。

### 实例属性

- **operationsOutsideApp**：拖动源建议的拖动到其他应用程序的操作。
- **operationsWithinApp**：拖动源建议在应用程序内进行的拖动操作。

## 配置拖放行为

- **DropConfiguration**：描述拖放行为。

## 符合

- 可复制
- 自定义调试字符串可转换


---
source: https://developer.apple.com/documentation/SwiftUI/DragConfiguration
crawled: 2025-12-02T17:42:38Z
---

# DragConfiguration

**Structure**

The behavior of the drag, proposed by the dragging source.

## Declaration

```swift
struct DragConfiguration
```

## Structures

- **DragConfiguration.OperationsOutsideApp**: Describes the suggested drag operations to other applications.
- **DragConfiguration.OperationsWithinApp**: Describes the drag operations suggested to destinations within the app.

## Initializers

- **init(allowMove:)**: Creates a drag configuration that can support drag-to-move in addition to drag-to-copy.
- **init(allowMove:allowDelete:)**: Creates a drag configuration that can support drag-to-move and drag-to-delete in addition to drag-to-copy.
- **init(operationsWithinApp:operationsOutsideApp:)**: Creates a default drag configuration with operation `.copy` support for drags within the application and to other applications.

## Instance Properties

- **operationsOutsideApp**: The operations suggested by the drag source for drags to other applications.
- **operationsWithinApp**: The operations suggested by the drag source for drags within the application.

## Configuring drag and drop behavior

- **DropConfiguration**: Describes the behavior of the drop.

## Conforms To

- Copyable
- CustomDebugStringConvertible

