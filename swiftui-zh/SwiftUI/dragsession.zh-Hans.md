---
来源： https://developer.apple.com/documentation/swiftui/dragsession
抓取时间： 2025-12-03T06:47:07Z
---

# DragSession

**Structure**

描述正在进行的拖动会话。

## 声明

```swift
struct DragSession
```

## 结构

- **DragSession.ID**：拖动会话的标识符。

## 实例属性

- **draggedItemIndex**：光标下被拖动项目的索引。
- **id**：拖动会话的标识符。
- **location**：拖动会话在本地坐标空间中的位置。
- **phase**：拖动过程的当前阶段。

### 实例方法

- **draggedItemIDs(for:)**：在项目符合`Identifiable` 协议或标识符已单独提供给 SwiftUI 的情况下，提供当前拖动项目的标识符数组。

## 枚举

- **DragSession.Phase**：当前拖动会话的阶段

## 移动项目

- **DropSession**

## 符合

- 可识别


---
source: https://developer.apple.com/documentation/swiftui/dragsession
crawled: 2025-12-03T06:47:07Z
---

# DragSession

**Structure**

Describes the ongoing dragging session.

## Declaration

```swift
struct DragSession
```

## Structures

- **DragSession.ID**: The identifier of a drag session.

## Instance Properties

- **draggedItemIndex**: The index of the dragged item under the cursor.
- **id**: The identifier of the drag session.
- **location**: Location of the drag session in the local coordinate space.
- **phase**: The current phase of the drag session.

## Instance Methods

- **draggedItemIDs(for:)**: Provides an array of identifiers of the currently dragged items in a case when the items conform to the `Identifiable` protocol, or identifiers were provided to SwiftUI separately.

## Enumerations

- **DragSession.Phase**: The phase of the current drag session

## Moving items

- **DropSession**

## Conforms To

- Identifiable

