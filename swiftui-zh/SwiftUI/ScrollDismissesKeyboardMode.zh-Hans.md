---
来源： https://developer.apple.com/documentation/SwiftUI/ScrollDismissesKeyboardMode
抓取时间： 2025-12-02T17:40:47Z
---

# 滚动解除键盘模式

**Structure**

可滚动内容与软件键盘交互的方式。

## 声明

```swift
struct ScrollDismissesKeyboardMode
```

## 概览

在调用[scrollDismissesKeyboard(_:)](View/scrollDismissesKeyboard.zh-Hans.md) 修改器时使用此类型可指定可滚动视图的取消行为。

## 获取模式

- **automatic**：根据周围环境自动确定模式。
- **immediately**：开始滚动时立即关闭键盘。
- **interactively**：使人们能够在滚动操作中交互式地取消键盘。
- **never**：切勿在滚动时自动取消键盘。

## 与软件键盘交互

- **scrollDismissesKeyboard(_:)**：配置可滚动内容与软件键盘交互的行为。
- **scrollDismissesKeyboardMode**：滚动内容与软件键盘的交互方式。

## 符合

- 可复制
- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollDismissesKeyboardMode
crawled: 2025-12-02T17:40:47Z
---

# ScrollDismissesKeyboardMode

**Structure**

The ways that scrollable content can interact with the software keyboard.

## Declaration

```swift
struct ScrollDismissesKeyboardMode
```

## Overview

Use this type in a call to the [scrollDismissesKeyboard(_:)](View/scrollDismissesKeyboard.zh-Hans.md) modifier to specify the dismissal behavior of scrollable views.

## Getting modes

- **automatic**: Determine the mode automatically based on the surrounding context.
- **immediately**: Dismiss the keyboard as soon as scrolling starts.
- **interactively**: Enable people to interactively dismiss the keyboard as part of the scroll operation.
- **never**: Never dismiss the keyboard automatically as a result of scrolling.

## Interacting with a software keyboard

- **scrollDismissesKeyboard(_:)**: Configures the behavior in which scrollable content interacts with the software keyboard.
- **scrollDismissesKeyboardMode**: The way that scrollable content interacts with the software keyboard.

## Conforms To

- Copyable
- Equatable
- Hashable
- Sendable
- SendableMetatype

