--- 来源：https://developer.apple.com/documentation/SwiftUI/DragConfiguration/OperationsOutsideApp-swift.struct

抓取时间：2025-12-03T06:46:46Z

---

# DragConfiguration.OperationsOutsideApp

**Structure**

描述建议的拖拽操作，使其指向其他应用程序。

## 声明

```swift
struct OperationsOutsideApp
```

## 概述

要创建默认配置，请初始化时不带任何参数。

在 iOS 上，默认行为是禁止拖拽到应用程序外部。在 macOS 上，支持拖拽复制到应用程序内部和其他应用程序的目标位置。

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
           let operations = OperationsOutsideApp(
               allowCopy: true, allowMove: true
           )
           return DragConfiguration(operationsOutsideApp: operations)
       }
   }
```

在上面的示例中，应用程序提供了一些操作，这些操作将被建议给其他应用程序。在应用程序内拖动到目标位置的操作将使用默认行为：建议使用 `copy` 操作来拖动目标位置。

## 初始化程序

- **init(allowCopy:)**：创建一个值，用于描述允许拖动到其他应用程序的操作。

- **init(allowCopy:allowMove:allowDelete:)**：创建一个值，用于描述允许拖动到其他应用程序的操作。

## 实例属性

- **allowAlias**：一个布尔值，指示拖动操作是否支持为放置的项目创建别名。

## 符合以下规范

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/DragConfiguration/OperationsOutsideApp-swift.struct
crawled: 2025-12-03T06:46:46Z
---

# DragConfiguration.OperationsOutsideApp

**Structure**

Describes the suggested drag operations to other applications.

## Declaration

```swift
struct OperationsOutsideApp
```

## Overview

To create a default configuration, initialize it without parameters.

On iOS, the default behavior is to disallow drag outside the application. On macOS—support drag-to-copy to destinations both within the application and to other apps.

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
           let operations = OperationsOutsideApp(
               allowCopy: true, allowMove: true
           )
           return DragConfiguration(operationsOutsideApp: operations)
       }
   }
```

In the example above, an application provides operations that will be suggested to other applications. Drags to destinations within the app will use the default behavior: suggest operation `copy` to drag destinations.

## Initializers

- **init(allowCopy:)**: Creates a value that describes the operations allowed for drags to other applications.
- **init(allowCopy:allowMove:allowDelete:)**: Creates a value that describes the operations allowed for drags to other applications.

## Instance Properties

- **allowAlias**: A Boolean value indicating if the drag operation supports creating aliases to the dropped items.

## Conforms To

- Sendable
- SendableMetatype

