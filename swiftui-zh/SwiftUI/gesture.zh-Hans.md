--- 来源：https://developer.apple.com/documentation/swiftui/gesture

抓取时间：2025-12-04T11:29:27Z

---

# 手势

**Protocol**

一个将事件序列与手势匹配的实例，并返回其每个状态的值流。

## 声明

```swift
@MainActor @preconcurrency protocol Gesture<Value>
```

## 概述

通过声明符合 `Gesture` 协议的类型来创建自定义手势。

## 实现自定义手势

- **body**：手势的内容和行为。

- **Body**：表示 `Self` 主体的手势类型。

## 执行手势

- **updating(_:body:)**：当手势值发生变化时，更新提供的手势状态属性。

- **onChanged(_:)**：添加一个在手势值发生变化时要执行的操作。

- **onEnded(_:)**：添加一个在手势结束时要执行的操作。

- **Value**：表示手势值的类型。

## 组合手势

- **simultaneously(with:)**：将一个手势与另一个手势组合，创建一个可以同时识别这两个手势的新手势。

- **sequenced(before:)**：将一个手势与另一个手势顺序排列，创建一个新手势，该手势只有在第一个手势成功后才会接收事件。

- **exclusively(before:)**：将两个手势组合成一个新手势，但只有一个手势生效，优先执行第一个手势。

## 为手势添加修饰键

- **modifiers(_:)**：将手势与键盘修饰键组合。

## 转换手势

- **map(_:)**：返回一个使用给定闭包映射此手势值的手势。

## 自定义手势激活

- **handActivationBehavior(_:)**：自定义手势在由手或类似手的输入驱动时的激活行为。

## 将手势与 RealityKit 实体一起使用

- **targetedToAnyEntity()**：要求此手势必须指向一个实体。

- **targetedToEntity(_:)**：要求此手势必须指向一个实体或其子实体。

- **targetedToEntity(where:)**：要求此手势指向查询结果中可找到的实体。

## 定义自定义手势

- **highPriorityGesture(_:including:)**：将手势附加到视图，其优先级高于视图定义的手势。

- **highPriorityGesture(_:isEnabled:)**：将手势附加到视图，其优先级高于视图定义的手势。

- **highPriorityGesture(_:name:isEnabled:)**：将手势附加到视图，其优先级高于视图定义的手势。

- **handGestureShortcut(_:isEnabled:)**：为修改后的控件分配手势快捷键。

- **defersSystemGestures(on:)**：设置手势优先于系统手势的屏幕边缘。

- **AnyGesture**：一种擦除输入的手势。

- **HandActivationBehavior**：一种专门用于手部输入的激活行为。

- **HandGestureShortcut**：手势快捷方式描述了用户可以通过手指和手腕的动作来激活按钮或切换开关。

## 符合规范的类型

- AnyGesture

- DragGesture

- ExclusiveGesture

- GestureStateGesture

- LongPressGesture

- MagnificationGesture

- MagnifyGesture

- RotateGesture

- RotateGesture3D

- RotationGesture

- SequenceGesture

- SimultaneousGesture

- SpatialEventGesture

- SpatialTapGesture

- TapGesture

- WindowDragGesture


---
source: https://developer.apple.com/documentation/swiftui/gesture
crawled: 2025-12-04T11:29:27Z
---

# Gesture

**Protocol**

An instance that matches a sequence of events to a gesture, and returns a stream of values for each of its states.

## Declaration

```swift
@MainActor @preconcurrency protocol Gesture<Value>
```

## Overview

Create custom gestures by declaring types that conform to the `Gesture` protocol.

## Implementing a custom gesture

- **body**: The content and behavior of the gesture.
- **Body**: The type of gesture representing the body of `Self`.

## Performing the gesture

- **updating(_:body:)**: Updates the provided gesture state property as the gesture’s value changes.
- **onChanged(_:)**: Adds an action to perform when the gesture’s value changes.
- **onEnded(_:)**: Adds an action to perform when the gesture ends.
- **Value**: The type representing the gesture’s value.

## Composing gestures

- **simultaneously(with:)**: Combines a gesture with another gesture to create a new gesture that recognizes both gestures at the same time.
- **sequenced(before:)**: Sequences a gesture with another one to create a new gesture, which results in the second gesture only receiving events after the first gesture succeeds.
- **exclusively(before:)**: Combines two gestures exclusively to create a new gesture where only one gesture succeeds, giving precedence to the first gesture.

## Adding modifier keys to a gesture

- **modifiers(_:)**: Combines a gesture with keyboard modifiers.

## Transforming a gesture

- **map(_:)**: Returns a gesture that uses the given closure to map over this gesture’s value.

## Customizing gesture activation

- **handActivationBehavior(_:)**: Customizes the activation behavior for a gesture when driven by hand or hand-like input.

## Using a gesture with a RealityKit entity

- **targetedToAnyEntity()**: Requires this gesture to target an entity.
- **targetedToEntity(_:)**: Requires this gesture to target an entity or a descendant of entity.
- **targetedToEntity(where:)**: Requires this gesture to target an entity that can be found in the results of the query.

## Defining custom gestures

- **highPriorityGesture(_:including:)**: Attaches a gesture to the view with a higher precedence than gestures defined by the view.
- **highPriorityGesture(_:isEnabled:)**: Attaches a gesture to the view with a higher precedence than gestures defined by the view.
- **highPriorityGesture(_:name:isEnabled:)**: Attaches a gesture to the view with a higher precedence than gestures defined by the view.
- **handGestureShortcut(_:isEnabled:)**: Assigns a hand gesture shortcut to the modified control.
- **defersSystemGestures(on:)**: Sets the screen edge from which you want your gesture to take precedence over the system gesture.
- **AnyGesture**: A type-erased gesture.
- **HandActivationBehavior**: An activation behavior specific to hand-driven input.
- **HandGestureShortcut**: Hand gesture shortcuts describe finger and wrist movements that the user can perform in order to activate a button or toggle.

## Conforming Types

- AnyGesture
- DragGesture
- ExclusiveGesture
- GestureStateGesture
- LongPressGesture
- MagnificationGesture
- MagnifyGesture
- RotateGesture
- RotateGesture3D
- RotationGesture
- SequenceGesture
- SimultaneousGesture
- SpatialEventGesture
- SpatialTapGesture
- TapGesture
- WindowDragGesture

