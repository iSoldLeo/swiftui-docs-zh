--- 来源：https://developer.apple.com/documentation/SwiftUI/Drag-and-drop
抓取时间：2025-12-02T17:41:25Z

---

# 拖放

**API 集合**

允许用户通过拖动将项目从一个位置移动或复制到另一个位置。

## 概述

拖放功能为用户提供了一种便捷的方式，让他们可以使用直观的拖动手势，将内容从应用的一个部分移动到另一个部分，或从一个应用移动到另一个应用。要支持此功能，请在应用界面中为潜在的源视图和目标视图添加视图修饰符。

在修饰符中，请提供或接受符合 [doc://com.apple.documentation/documentation/CoreTransferable/Transferable] 协议的类型，或继承自 [doc://com.apple.documentation/documentation/Foundation/NSItemProvider] 类的类型。尽可能使用可转移的项目。

有关设计指南，请参阅《人机界面指南》中的 [doc://com.apple.documentation/design/Human-Interface-Guidelines/drag-and-drop]。

## 基本功能

- **使用 SwiftUI 实现拖放功能**：在列表、表格和自定义视图中启用拖放交互。

- **将视图设置为拖放源**：采用可拖放 API 为拖放操作提供项目。

## 配置拖放行为

- **DragConfiguration**：拖放源提出的拖放行为。

- **DropConfiguration**：描述放置行为。

## 移动项目

- **DragSession**：描述正在进行的拖放会话。

- **DropSession**

## 移动可转移项目

- **draggable(_:)**：激活此视图作为拖放操作的源。

- **draggable(_:preview:)**：激活此视图作为拖放操作的源。

- **dropDestination(for:action:isTargeted:)**：定义拖放操作的目标位置，该位置使用您指定的闭包处理拖放的内容。

## 使用项目提供程序移动项目

- **itemProvider(_:)**：提供一个闭包，用于提供特定数据元素的拖放表示形式。

- **onDrag(_:preview:)**：激活此视图作为拖放操作的源。

- **onDrag(_:)**：激活此视图作为拖放操作的源。

- **onDrop(of:isTargeted:perform:)**：定义拖放操作的目标位置，该位置使用您指定的闭包处理拖放的内容。

- **onDrop(of:delegate:)**：定义拖放操作的目标位置，该位置的行为由您提供的委托控制。

- **DropDelegate**：您实现的接口，用于与已修改为接受拖放操作的视图中的拖放操作进行交互。

- **DropProposal**：拖放操作的行为。

- **DropOperation**：操作类型，用于确定用户放置拖放项时拖放会话的解析方式。

- **DropInfo**：拖放操作的当前状态。

## 描述预览格式

- **DragDropPreviewsFormation**：在 macOS 上，描述拖动预览的视觉组成方式。拖放源和目标位置都可以指定所需的预览格式。

## 配置弹簧加载

- **springLoadingBehavior(_:)**：设置此视图的弹簧加载行为。

- **springLoadingBehavior**：设置与此环境关联的视图的弹簧加载交互行为。

- **SpringLoadingBehavior**：设置用于控制视图弹簧加载行为的选项。

## 事件处理

- **Gestures**：定义从点击、轻触、滑动到更精细手势的交互方式。

- **输入事件**：响应来自硬件设备（例如键盘或触控栏）的输入。

- **Clipboard**：允许用户通过发出复制和粘贴命令来移动或复制项目。

- **Focus**：识别并控制哪些可见对象响应用户交互。

- **系统事件**：响应系统事件，例如打开 URL。


---
source: https://developer.apple.com/documentation/SwiftUI/Drag-and-drop
crawled: 2025-12-02T17:41:25Z
---

# Drag and drop

**API Collection**

Enable people to move or duplicate items by dragging them from one location to another.

## Overview

Drag and drop offers people a convenient way to move content from one part of your app to another, or from one app to another, using an intuitive dragging gesture. Support this feature in your app by adding view modifiers to potential source and destination views within your app’s interface.



In your modifiers, provide or accept types that conform to the [doc://com.apple.documentation/documentation/CoreTransferable/Transferable] protocol, or that inherit from the [doc://com.apple.documentation/documentation/Foundation/NSItemProvider] class. When possible, prefer using transferable items.

For design guidance, see [doc://com.apple.documentation/design/Human-Interface-Guidelines/drag-and-drop] in the Human Interface Guidelines.

## Essentials

- **Adopting drag and drop using SwiftUI**: Enable drag-and-drop interactions in lists, tables and custom views.
- **Making a view into a drag source**: Adopt draggable API to provide items for drag-and-drop operations.

## Configuring drag and drop behavior

- **DragConfiguration**: The behavior of the drag, proposed by the dragging source.
- **DropConfiguration**: Describes the behavior of the drop.

## Moving items

- **DragSession**: Describes the ongoing dragging session.
- **DropSession**

## Moving transferable items

- **draggable(_:)**: Activates this view as the source of a drag and drop operation.
- **draggable(_:preview:)**: Activates this view as the source of a drag and drop operation.
- **dropDestination(for:action:isTargeted:)**: Defines the destination of a drag and drop operation that handles the dropped content with a closure that you specify.

## Moving items using item providers

- **itemProvider(_:)**: Provides a closure that vends the drag representation to be used for a particular data element.
- **onDrag(_:preview:)**: Activates this view as the source of a drag and drop operation.
- **onDrag(_:)**: Activates this view as the source of a drag and drop operation.
- **onDrop(of:isTargeted:perform:)**: Defines the destination of a drag-and-drop operation that handles the dropped content with a closure that you specify.
- **onDrop(of:delegate:)**: Defines the destination of a drag and drop operation using behavior controlled by the delegate that you provide.
- **DropDelegate**: An interface that you implement to interact with a drop operation in a view modified to accept drops.
- **DropProposal**: The behavior of a drop.
- **DropOperation**: Operation types that determine how a drag and drop session resolves when the user drops a drag item.
- **DropInfo**: The current state of a drop.

## Describing preview formations

- **DragDropPreviewsFormation**: On macOS, describes the way the dragged previews are visually composed. Both drag sources and drop destination can specify their desired preview formation.

## Configuring spring loading

- **springLoadingBehavior(_:)**: Sets the spring loading behavior this view.
- **springLoadingBehavior**: The behavior of spring loaded interactions for the views associated with this environment.
- **SpringLoadingBehavior**: The options for controlling the spring loading behavior of views.

## Event handling

- **Gestures**: Define interactions from taps, clicks, and swipes to fine-grained gestures.
- **Input events**: Respond to input from a hardware device, like a keyboard or a Touch Bar.
- **Clipboard**: Enable people to move or duplicate items by issuing Copy and Paste commands.
- **Focus**: Identify and control which visible object responds to user interaction.
- **System events**: React to system events, like opening a URL.

