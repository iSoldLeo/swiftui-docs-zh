--- 来源：https://developer.apple.com/documentation/SwiftUI/DropDelegate
抓取时间：2025-12-02T17:42:52Z

---

# DropDelegate

**Protocol**

一个用于与已修改为接受拖放操作的视图中的拖放操作进行交互的接口。

## 声明

```swift
@MainActor @preconcurrency protocol DropDelegate
```

## 概述

[DropDelegate](DropDelegate.zh-Hans.md) 协议提供了一种全面而灵活的方式来与拖放操作进行交互。当您使用 [onDrop(of:delegate:)](View/onDrop_of_delegate.zh-Hans.md) 方法修改视图以接受拖放操作时，请指定一个拖放委托。

或者，对于不需要拖放委托全部功能的简单拖放情况，您可以使用 [onDrop(of:isTargeted:perform:)](View/onDrop_of_isTargeted_perform.zh-Hans.md) 方法修改视图以接受拖放操作。此方法使用您在修饰符中提供的闭包来处理放置操作。

## 接收放置信息

- **dropEntered(info:)**：告知代理，一个经过验证的放置操作已进入修改后的视图。

- **dropExited(info:)**：告知代理，一个经过验证的放置操作已退出修改后的视图。

- **dropUpdated(info:)**：告知代理，一个经过验证的放置操作已移动到修改后的视图内部。

- **validateDrop(info:)**：告知代理，一个包含符合预期类型的物品的放置操作已进入接受放置操作的视图。

- **performDrop(info:)**：告知代理，它可以根据给定的信息请求物品提供程序的数据。

## 使用项目提供程序移动项目

- **itemProvider(_:)**：提供一个闭包，用于提供特定数据元素的拖放表示形式。

- **onDrag(_:preview:)**：激活此视图作为拖放操作的源。

- **onDrag(_:)**：激活此视图作为拖放操作的源。

- **onDrop(of:isTargeted:perform:)**：定义拖放操作的目标位置，该目标位置使用您指定的闭包处理放置的内容。

- **onDrop(of:delegate:)**：定义拖放操作的目标位置，该目标位置使用您提供的委托控制的行为。

- **DropProposal**：放置操作的行为。

- **DropOperation**：操作类型，用于确定用户放下拖放项时拖放会话的最终状态。

- **DropInfo**：拖放操作的当前状态。


---
source: https://developer.apple.com/documentation/SwiftUI/DropDelegate
crawled: 2025-12-02T17:42:52Z
---

# DropDelegate

**Protocol**

An interface that you implement to interact with a drop operation in a view modified to accept drops.

## Declaration

```swift
@MainActor @preconcurrency protocol DropDelegate
```

## Overview

The [DropDelegate](DropDelegate.zh-Hans.md) protocol provides a comprehensive and flexible way to interact with a drop operation. Specify a drop delegate when you modify a view to accept drops with the [onDrop(of:delegate:)](View/onDrop_of_delegate.zh-Hans.md) method.

Alternatively, for simple drop cases that don’t require the full functionality of a drop delegate, you can modify a view to accept drops using the [onDrop(of:isTargeted:perform:)](View/onDrop_of_isTargeted_perform.zh-Hans.md) method. This method handles the drop using a closure you provide as part of the modifier.

## Receiving drop information

- **dropEntered(info:)**: Tells the delegate a validated drop has entered the modified view.
- **dropExited(info:)**: Tells the delegate a validated drop operation has exited the modified view.
- **dropUpdated(info:)**: Tells the delegate that a validated drop moved inside the modified view.
- **validateDrop(info:)**: Tells the delegate that a drop containing items conforming to one of the expected types entered a view that accepts drops.
- **performDrop(info:)**: Tells the delegate it can request the item provider data from the given information.

## Moving items using item providers

- **itemProvider(_:)**: Provides a closure that vends the drag representation to be used for a particular data element.
- **onDrag(_:preview:)**: Activates this view as the source of a drag and drop operation.
- **onDrag(_:)**: Activates this view as the source of a drag and drop operation.
- **onDrop(of:isTargeted:perform:)**: Defines the destination of a drag-and-drop operation that handles the dropped content with a closure that you specify.
- **onDrop(of:delegate:)**: Defines the destination of a drag and drop operation using behavior controlled by the delegate that you provide.
- **DropProposal**: The behavior of a drop.
- **DropOperation**: Operation types that determine how a drag and drop session resolves when the user drops a drag item.
- **DropInfo**: The current state of a drop.

