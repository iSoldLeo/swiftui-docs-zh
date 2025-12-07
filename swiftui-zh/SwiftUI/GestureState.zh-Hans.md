---

来源：https://developer.apple.com/documentation/SwiftUI/GestureState
抓取时间：2025-12-02T17:41:20Z

---

# GestureState

**Structure**

一种属性包装类型，用于在用户执行手势时更新属性，并在手势结束后将属性重置为初始状态。

## 声明

```swift
@propertyWrapper @frozen struct GestureState<Value>
```

## 概述

将属性声明为 `@GestureState`，将其绑定并作为参数传递给手势的 [updating(_:body:)](Gesture/updating___body.zh-Hans.md) 回调函数，即可接收其更新。声明为 `@GestureState` 的属性会在手势变为非活动状态时隐式重置，因此适合跟踪瞬态状态。

为 [Circle](Circle.zh-Hans.md) 添加长按手势，并在手势期间通过声明属性 `@GestureState` 来更新界面：

```swift
struct SimpleLongPressGestureView: View {
    @GestureState private var isDetectingLongPress = false

    var longPress: some Gesture {
        LongPressGesture(minimumDuration: 3)
            .updating($isDetectingLongPress) { currentState, gestureState, transaction in
                gestureState = currentState
            }
    }

    var body: some View {
        Circle()
            .fill(self.isDetectingLongPress ? Color.red : Color.green)
            .frame(width: 100, height: 100, alignment: .center)
            .gesture(longPress)
    }
}
```

## 创建手势状态

- **init(initialValue:)**：创建一个从手势派生的视图状态，并为其指定初始值。

- **init(initialValue:reset:)**：创建一个从手势派生的视图状态，并为其指定初始状态值和一个用于重置该状态的事务闭包。

- **init(initialValue:resetTransaction:)**：创建一个从手势派生的视图状态，并为其指定初始状态值和一个用于重置该状态的事务。

- **init(reset:)**：创建一个从手势派生的视图状态，并为其指定一个用于重置该状态的事务闭包。

- **init(resetTransaction:)**：创建一个基于手势的视图状态，并附带一个用于重置该状态的事务。

- **init(wrappedValue:)**：创建一个基于手势的视图状态。

- **init(wrappedValue:reset:)**：创建一个基于手势的视图状态，该状态包含一个包装后的状态值和一个用于重置该状态的事务闭包。

- **init(wrappedValue:resetTransaction:)**：创建一个基于手势的视图状态，该状态包含一个包装后的状态值和一个用于重置该状态的事务。

## 获取状态

- **wrappedValue**：手势状态属性引用的包装值。

- **projectedValue**：手势状态属性的绑定。

## 管理手势状态

- **GestureStateGesture**：一种用于更新手势更新回调函数所返回状态的手势。

## 符合以下规范

- DynamicProperty

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/GestureState
crawled: 2025-12-02T17:41:20Z
---

# GestureState

**Structure**

A property wrapper type that updates a property while the user performs a gesture and resets the property back to its initial state when the gesture ends.

## Declaration

```swift
@propertyWrapper @frozen struct GestureState<Value>
```

## Overview

Declare a property as `@GestureState`, pass as a binding to it as a parameter to a gesture’s [updating(_:body:)](Gesture/updating___body.zh-Hans.md) callback, and receive updates to it. A property that’s declared as `@GestureState` implicitly resets when the gesture becomes inactive, making it suitable for tracking transient state.

Add a long-press gesture to a [Circle](Circle.zh-Hans.md), and update the interface during the gesture by declaring a property as `@GestureState`:

```swift
struct SimpleLongPressGestureView: View {
    @GestureState private var isDetectingLongPress = false

    var longPress: some Gesture {
        LongPressGesture(minimumDuration: 3)
            .updating($isDetectingLongPress) { currentState, gestureState, transaction in
                gestureState = currentState
            }
    }

    var body: some View {
        Circle()
            .fill(self.isDetectingLongPress ? Color.red : Color.green)
            .frame(width: 100, height: 100, alignment: .center)
            .gesture(longPress)
    }
}
```

## Creating a gesture state

- **init(initialValue:)**: Creates a view state that’s derived from a gesture with an initial value.
- **init(initialValue:reset:)**: Creates a view state that’s derived from a gesture with an initial state value and a closure that provides a transaction to reset it.
- **init(initialValue:resetTransaction:)**: Creates a view state that’s derived from a gesture with an initial state value and a transaction to reset it.
- **init(reset:)**: Creates a view state that’s derived from a gesture with a closure that provides a transaction to reset it.
- **init(resetTransaction:)**: Creates a view state that’s derived from a gesture with a transaction to reset it.
- **init(wrappedValue:)**: Creates a view state that’s derived from a gesture.
- **init(wrappedValue:reset:)**: Creates a view state that’s derived from a gesture with a wrapped state value and a closure that provides a transaction to reset it.
- **init(wrappedValue:resetTransaction:)**: Creates a view state that’s derived from a gesture with a wrapped state value and a transaction to reset it.

## Getting the state

- **wrappedValue**: The wrapped value referenced by the gesture state property.
- **projectedValue**: A binding to the gesture state property.

## Managing gesture state

- **GestureStateGesture**: A gesture that updates the state provided by a gesture’s updating callback.

## Conforms To

- DynamicProperty
- Sendable
- SendableMetatype

