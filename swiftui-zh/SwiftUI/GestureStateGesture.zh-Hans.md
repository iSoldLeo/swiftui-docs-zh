--- 来源：https://developer.apple.com/documentation/SwiftUI/GestureStateGesture
抓取时间：2025-12-02T17:41:21Z

---

# GestureStateGesture

**Structure**

一种用于更新手势更新回调提供的状态的手势。

## 声明

```swift
@frozen struct GestureStateGesture<Base, State> where Base : Gesture
```

## 概述

手势的 [updating(_:body:)](Gesture/updating___body.zh-Hans.md) 回调返回一个 `GestureStateGesture` 实例，用于更新带有 [GestureState](GestureState.zh-Hans.md) 属性包装器注解的瞬态属性。

## 创建正在进行的手势

- **init(base:state:body:)**：创建一个由正在进行的手势生成的新手势。

- **base**：原始手势。

- **state**：用户执行手势时会发生变化的值。

## 支持类型

- **body**：更新手势，包含原始手势的值、手势的更新状态以及事务。

## 管理手势状态

- **GestureState**：属性包装类型，在用户执行手势时更新属性，并在手势结束后将属性重置为初始状态。

## 符合以下协议：

- 手势


---
source: https://developer.apple.com/documentation/SwiftUI/GestureStateGesture
crawled: 2025-12-02T17:41:21Z
---

# GestureStateGesture

**Structure**

A gesture that updates the state provided by a gesture’s updating callback.

## Declaration

```swift
@frozen struct GestureStateGesture<Base, State> where Base : Gesture
```

## Overview

A gesture’s [updating(_:body:)](Gesture/updating___body.zh-Hans.md) callback returns a `GestureStateGesture` instance for updating a transient state property that’s annotated with the [GestureState](GestureState.zh-Hans.md) property wrapper.

## Creating an in-progress gesture

- **init(base:state:body:)**: Creates a new gesture that’s the result of an ongoing gesture.
- **base**: The originating gesture.
- **state**: A value that changes as the user performs the gesture.

## Supporting types

- **body**: The updating gesture containing the originating gesture’s value, the updated state of the gesture, and a transaction.

## Managing gesture state

- **GestureState**: A property wrapper type that updates a property while the user performs a gesture and resets the property back to its initial state when the gesture ends.

## Conforms To

- Gesture

