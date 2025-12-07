---
来源：https://developer.apple.com/documentation/SwiftUI/GestureStateGesture/init(base:state:body:)
抓取时间： 2025-12-03T06:44:22Z
---

# init(base:state:body:)

**Initializer**

创建一个新手势，它是正在进行的手势的结果。

## 声明

```swift
init(base: Base, state: GestureState<State>, body: @escaping (GestureStateGesture<Base, State>.Value, inout State, inout Transaction) -> Void)
```

## 参数

- **base**：初始手势。
- **state**：[GestureState](../GestureState.zh-Hans.md)属性的包装值。
- **body**：SwiftUI 在手势值发生变化时调用的回调。

## 创建一个进行中的手势

- **base**：初始手势。
- **state**：随着用户执行手势而变化的值。


---
source: https://developer.apple.com/documentation/SwiftUI/GestureStateGesture/init(base:state:body:)
crawled: 2025-12-03T06:44:22Z
---

# init(base:state:body:)

**Initializer**

Creates a new gesture that’s the result of an ongoing gesture.

## Declaration

```swift
init(base: Base, state: GestureState<State>, body: @escaping (GestureStateGesture<Base, State>.Value, inout State, inout Transaction) -> Void)
```

## Parameters

- **base**: The originating gesture.
- **state**: The wrapped value of a [GestureState](../GestureState.zh-Hans.md) property.
- **body**: The callback that SwiftUI invokes as the gesture’s value changes.

## Creating an in-progress gesture

- **base**: The originating gesture.
- **state**: A value that changes as the user performs the gesture.

