--- 来源：https://developer.apple.com/documentation/SwiftUI/Transaction
抓取时间：2025-12-02T17:34:33Z

---

# 事务

**Structure**

当前状态处理更新的上下文。

## 声明

```swift
@frozen struct Transaction
```

## 概述

使用事务在视图层级结构中的视图之间传递动画。

状态更改的根事务来自发生更改的绑定，以及通过调用 [withTransaction(_:_:)](withTransaction.zh-Hans.md) 或 [withAnimation(_:_:)](withAnimation.zh-Hans.md) 设置的任何全局值。

## 创建事务

- **init()**：创建事务。

- **init(animation:)**：创建事务并为其动画属性赋值。

## 管理动画

- **animation**：与当前状态更改关联的动画（如有）。

- **disablesAnimations**：一个布尔值，指示视图是否应禁用动画。

- **addAnimationCompletion(criteria:_:)**：添加一个完成事件，当使用此事务创建的所有动画全部完成后运行。

## 管理窗口关闭

- **dismissBehavior**：与 [DismissWindowAction](DismissWindowAction.zh-Hans.md) 结合使用时，窗口以编程方式关闭的行为。

## 获取事务信息

- **isContinuous**：一个布尔值，指示事务是否源自生成一系列值的操作。

- **scrollTargetAnchor**：滚动到视图时，视图在其可见区域内的首选对齐方式。

- **tracksVelocity**：此事务是否会跟踪任何可动画属性的更改速度。

- **subscript(_:)**：访问与自定义键关联的事务值。

## 实例属性

- **scrollContentOffsetAdjustmentBehavior**：滚动视图在当前事务中对内容偏移调整的行为。

- **scrollPositionUpdatePreservesVelocity**：对滚动视图的滚动位置进行编程更新时，是否会保留滚动视图中任何活动滚动的当前速度。

## 将动画移动到另一个视图

- **withTransaction(_:_:)**：使用指定的事务执行闭包并返回结果。

- **withTransaction(_:_:_:)**：使用指定的事务键路径和值执行闭包并返回结果。

- **transaction(_:)**：将给定的事务变更函数应用于视图中使用的所有动画。

- **transaction(value:_:)**：将给定的事务变更函数应用于视图中使用的所有动画。

- **transaction(_:body:)**：将给定的事务变更函数应用于 `body` 闭包中使用的所有动画。

- **Entry()**：创建环境值、事务、容器值或焦点值条目。

- **TransactionKey**：用于访问事务中值的键。


---
source: https://developer.apple.com/documentation/SwiftUI/Transaction
crawled: 2025-12-02T17:34:33Z
---

# Transaction

**Structure**

The context of the current state-processing update.

## Declaration

```swift
@frozen struct Transaction
```

## Overview

Use a transaction to pass an animation between views in a view hierarchy.

The root transaction for a state change comes from the binding that changed, plus any global values set by calling [withTransaction(_:_:)](withTransaction.zh-Hans.md) or [withAnimation(_:_:)](withAnimation.zh-Hans.md).

## Creating a transaction

- **init()**: Creates a transaction.
- **init(animation:)**: Creates a transaction and assigns its animation property.

## Managing animations

- **animation**: The animation, if any, associated with the current state change.
- **disablesAnimations**: A Boolean value that indicates whether views should disable animations.
- **addAnimationCompletion(criteria:_:)**: Adds a completion to run when the animations created with this transaction are all complete.

## Managing window dismissal

- **dismissBehavior**: The behavior for how windows will dismiss programmatically when used in conjunction with [DismissWindowAction](DismissWindowAction.zh-Hans.md).

## Getting information about a transaction

- **isContinuous**: A Boolean value that indicates whether the transaction originated from an action that produces a sequence of values.
- **scrollTargetAnchor**: The preferred alignment of the view within a scroll view’s visible region when scrolling to a view.
- **tracksVelocity**: Whether this transaction will track the velocity of any animatable properties that change.
- **subscript(_:)**: Accesses the transaction value associated with a custom key.

## Instance Properties

- **scrollContentOffsetAdjustmentBehavior**: The behavior a scroll view will have regarding content offset adjustments for the current transaction.
- **scrollPositionUpdatePreservesVelocity**: Whether a programmatic update to the scroll position of a scroll view preserves the current velocity of any active scroll of the scroll view.

## Moving an animation to another view

- **withTransaction(_:_:)**: Executes a closure with the specified transaction and returns the result.
- **withTransaction(_:_:_:)**: Executes a closure with the specified transaction key path and value and returns the result.
- **transaction(_:)**: Applies the given transaction mutation function to all animations used within the view.
- **transaction(value:_:)**: Applies the given transaction mutation function to all animations used within the view.
- **transaction(_:body:)**: Applies the given transaction mutation function to all animations used within the `body` closure.
- **Entry()**: Creates an environment values, transaction, container values, or focused values entry.
- **TransactionKey**: A key for accessing values in a transaction.

