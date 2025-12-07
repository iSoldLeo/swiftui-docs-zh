---
来源： https://developer.apple.com/documentation/SwiftUI/ImmersionChangeContext
抓取时间： 2025-12-02T17:22:01Z
---

# 沉浸式更改上下文

**Structure**

表示应用程序沉浸状态的结构。

## 声明

```swift
struct ImmersionChangeContext
```

## 概览

您不会直接使用此结构。相反，SwiftUI 通过`onImmersionChange` 修改器的闭包提供此结构的实例。

## 实例属性

- **amount**：当前的浸入量。

## 响应浸入度变化

- **onImmersionChange(initial:_:)**：当应用程序的沉浸状态发生变化时执行操作。

## 符合

- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/ImmersionChangeContext
crawled: 2025-12-02T17:22:01Z
---

# ImmersionChangeContext

**Structure**

A structure that represents a state of immersion of your app.

## Declaration

```swift
struct ImmersionChangeContext
```

## Overview

You don’t use this structure directly. Instead, SwiftUI provides instances of this structure via the `onImmersionChange` modifier’s closure.

## Instance Properties

- **amount**: The current amount of immersion.

## Responding to immersion changes

- **onImmersionChange(initial:_:)**: Performs an action when the immersion state of your app changes.

## Conforms To

- Sendable
- SendableMetatype

