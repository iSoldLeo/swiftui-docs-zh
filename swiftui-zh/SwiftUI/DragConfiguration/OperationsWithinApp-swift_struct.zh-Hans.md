--- 来源：https://developer.apple.com/documentation/SwiftUI/DragConfiguration/OperationsWithinApp-swift.struct

抓取时间：2025-12-03T06:46:47Z

---

# DragConfiguration.OperationsWithinApp

**Structure**

描述应用内建议的拖拽操作。

## 声明

```swift
struct OperationsWithinApp
```

## 概述

要创建默认配置，请初始化时不带任何参数。

在 iOS 上，默认行为是允许在应用内拖拽复制。在 macOS 上，默认配置是支持拖拽复制到应用内和其他应用。

除了 `copy` 之外，还可以通过在初始化程序中指定来添加 `move` 操作支持：

```swift
   struct DraggableBookView: View {
       var id: UUID

       var body: some View {
           BookView()
               .draggable(Book(id: id))
               .dragConfiguration(makeConfiguration())
       }

       func makeConfiguration() -> DragConfiguration {
           let operations = OperationsWithinApp(allowMove: true)
           return DragConfiguration(operationsWithinApp: operations)
       }
   }
```

在上面的示例中，应用程序提供了一些操作，这些操作将被建议用于应用程序内的目标位置。拖拽到其他应用程序的操作将使用默认行为：建议在 macOS 上拖拽目标位置时执行 `copy` 操作，并在 iOS 上禁止拖拽。

## 初始化程序

- **init(allowCopy:allowMove:allowDelete:)**：创建一个值，用于描述在应用程序内结束的拖拽操作所允许的操作。

- **init(allowMove:)**：创建一个值，用于描述在应用程序内结束的拖拽操作所允许的操作。复制操作始终允许。

## 实例属性

- **allowAlias**：一个布尔值，指示拖放操作是否支持为拖放项创建别名。

## 符合以下标准

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/DragConfiguration/OperationsWithinApp-swift.struct
crawled: 2025-12-03T06:46:47Z
---

# DragConfiguration.OperationsWithinApp

**Structure**

Describes the drag operations suggested to destinations within the app.

## Declaration

```swift
struct OperationsWithinApp
```

## Overview

To create a default configuration, initialize it without parameters.

On iOS, the default behavior is to allow drag-to-copy within the application. On macOS, the default configuration is to support drag-to-copy to destinations both within the application and to other apps.

In addition to `copy`, add `move` operation support by specifying that in the initializer:

```swift
   struct DraggableBookView: View {
       var id: UUID

       var body: some View {
           BookView()
               .draggable(Book(id: id))
               .dragConfiguration(makeConfiguration())
       }

       func makeConfiguration() -> DragConfiguration {
           let operations = OperationsWithinApp(allowMove: true)
           return DragConfiguration(operationsWithinApp: operations)
       }
   }
```

In the example above, an application provides operations that will be suggested to destinations within the app. Drags to other apps will use the default behavior: suggest operation `copy` to drag destinations on macOS, and forbid drags on iOS.

## Initializers

- **init(allowCopy:allowMove:allowDelete:)**: Creates a value that describes the operations allowed for drags that end within the application.
- **init(allowMove:)**: Creates a value that describes the operations allowed for drags that end within the application. Copy operation is always allowed.

## Instance Properties

- **allowAlias**: A Boolean value indicating if the drag operation supports creating aliases to the dropped items.

## Conforms To

- Sendable
- SendableMetatype

