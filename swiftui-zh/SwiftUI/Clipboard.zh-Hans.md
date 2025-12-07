---

来源：https://developer.apple.com/documentation/SwiftUI/Clipboard

抓取时间：2025-12-02T17:41:24Z

---

# 剪贴板

**API 集合**

使用户能够通过发出复制和粘贴命令来移动或复制项目。

## 概述

当用户发出标准的复制和剪切命令时，他们希望将项目移动到系统的剪贴板，然后从剪贴板将项目粘贴到同一应用内的其他位置或另一个应用中。如果您添加视图修饰符来指示如何响应标准命令，您的应用就可以参与此活动。

在您的复制和粘贴修饰符中，提供或接受符合 [doc://com.apple.documentation/documentation/CoreTransferable/Transferable] 协议或继承自 [doc://com.apple.documentation/documentation/Foundation/NSItemProvider] 类的类型。尽可能优先使用可转移的项目。

## 复制可转移项目

- **copyable(_:)**：指定响应系统“复制”命令而要复制的项目列表。

- **cuttable(for:action:)**：指定响应系统“剪切”命令而将项目移动到剪贴板的操作。

- **pasteDestination(for:action:validator:)**：指定响应系统“粘贴”命令而将已验证的项目添加到视图的操作。

## 使用项目提供程序复制项目

- **onCopyCommand(perform:)**：添加响应系统“复制”命令而要执行的操作。

- **onCutCommand(perform:)**：添加响应系统“剪切”命令而要执行的操作。

- **onPasteCommand(of:perform:)**：添加响应系统“粘贴”命令而要执行的操作。

- **onPasteCommand(of:validator:perform:)**：添加一个操作，用于响应系统“粘贴”命令，并验证粘贴的项目。

## 事件处理

- **Gestures**：定义从轻点、点击、滑动到更精细的手势等各种交互方式。

- **输入事件**：响应来自硬件设备（例如键盘或触控栏）的输入。

- **拖放**：允许用户通过拖动来移动或复制项目。

- **Focus**：识别并控制哪些可见对象响应用户交互。

- **系统事件**：响应系统事件，例如打开 URL。


---
source: https://developer.apple.com/documentation/SwiftUI/Clipboard
crawled: 2025-12-02T17:41:24Z
---

# Clipboard

**API Collection**

Enable people to move or duplicate items by issuing Copy and Paste commands.

## Overview

When people issue standard Copy and Cut commands, they expect to move items to the system’s Clipboard, from which they can paste the items into another place in the same app or into another app. Your app can participate in this activity if you add view modifiers that indicate how to respond to the standard commands.



In your copy and paste modifiers, provide or accept types that conform to the [doc://com.apple.documentation/documentation/CoreTransferable/Transferable] protocol, or that inherit from the [doc://com.apple.documentation/documentation/Foundation/NSItemProvider] class. When possible, prefer using transferable items.

## Copying transferable items

- **copyable(_:)**: Specifies a list of items to copy in response to the system’s Copy command.
- **cuttable(for:action:)**: Specifies an action that moves items to the Clipboard in response to the system’s Cut command.
- **pasteDestination(for:action:validator:)**: Specifies an action that adds validated items to a view in response to the system’s Paste command.

## Copying items using item providers

- **onCopyCommand(perform:)**: Adds an action to perform in response to the system’s Copy command.
- **onCutCommand(perform:)**: Adds an action to perform in response to the system’s Cut command.
- **onPasteCommand(of:perform:)**: Adds an action to perform in response to the system’s Paste command.
- **onPasteCommand(of:validator:perform:)**: Adds an action to perform in response to the system’s Paste command with items that you validate.

## Event handling

- **Gestures**: Define interactions from taps, clicks, and swipes to fine-grained gestures.
- **Input events**: Respond to input from a hardware device, like a keyboard or a Touch Bar.
- **Drag and drop**: Enable people to move or duplicate items by dragging them from one location to another.
- **Focus**: Identify and control which visible object responds to user interaction.
- **System events**: React to system events, like opening a URL.

