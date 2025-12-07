--- 来源：https://developer.apple.com/documentation/SwiftUI/Adding-Interactivity-with-Gestures

抓取时间：2025-12-02T17:40:49Z

---

# 使用手势添加交互性

**Article**

使用手势修饰符为您的应用添加交互性。

## 概述

手势修饰符处理处理用户输入事件（例如触摸）所需的所有逻辑，并识别这些事件何时与已知的手势模式（例如长按或旋转）匹配。识别到模式后，SwiftUI 会运行一个回调函数，您可以使用该回调函数来更新视图的状态或执行操作。

### 向视图添加手势修饰符

您添加的每个手势都应用于视图层次结构中的特定视图。要识别特定视图上的手势事件，请创建并配置该手势，然后使用 [gesture(_:including:)](View/gesture___including.zh-Hans.md) 修饰符：

```swift
struct ShapeTapView: View {
    var body: some View {
        let tap = TapGesture()
            .onEnded { _ in
                print("View tapped!")
            }
        
        return Circle()
            .fill(Color.blue)
            .frame(width: 100, height: 100, alignment: .center)
            .gesture(tap)
    }
}
```

### 响应手势回调

根据您添加到手势修饰符的回调，SwiftUI 会在手势状态发生变化时向您的代码报告。手势修饰符提供三种接收更新的方式：[updating(_:body:)](Gesture/updating___body.zh-Hans.md)、[onChanged(_:)](Gesture/onChanged.zh-Hans.md) 和 [onEnded(_:)](Gesture/onEnded.zh-Hans.md)。

#### 更新瞬态 UI 状态

要在手势变化时更新视图，请向视图添加 [GestureState](GestureState.zh-Hans.md) 属性，并在 [updating(_:body:)](Gesture/updating___body.zh-Hans.md) 回调中更新它。SwiftUI 会在识别到手势后以及手势值发生变化时立即调用更新回调。例如，SwiftUI 会在放大手势开始时立即调用更新回调，并在放大倍数发生变化时再次调用。当用户结束或取消手势时，SwiftUI 不会调用更新回调。相反，手势状态属性会自动将其状态重置为初始值。

例如，要创建一个在用户长按时改变颜色的视图，请添加一个手势状态属性并在更新回调中更新它。

```swift
struct CounterView: View {
    @GestureState private var isDetectingLongPress = false
    
    var body: some View {
        let press = LongPressGesture(minimumDuration: 1)
            .updating($isDetectingLongPress) { currentState, gestureState, transaction in
                gestureState = currentState
            }
        
        return Circle()
            .fill(isDetectingLongPress ? Color.yellow : Color.green)
            .frame(width: 100, height: 100, alignment: .center)
            .gesture(press)
    }
}
```

#### 在手势期间更新永久状态

要跟踪手势的变化（这些变化在手势结束后不应重置），请使用 [onChanged(_:)](Gesture/onChanged.zh-Hans.md) 回调。例如，要统计应用识别长按的次数，请添加 [onChanged(_:)](Gesture/onChanged.zh-Hans.md) 回调并递增计数器。

```swift
struct CounterView: View {
    @GestureState private var isDetectingLongPress = false
    @State private var totalNumberOfTaps = 0
    
    var body: some View {
        let press = LongPressGesture(minimumDuration: 1)
            .updating($isDetectingLongPress) { currentState, gestureState, transaction in
                gestureState = currentState
            }.onChanged { _ in
                self.totalNumberOfTaps += 1
            }
        
        return VStack {
            Text("\(totalNumberOfTaps)")
                .font(.largeTitle)
            
            Circle()
                .fill(isDetectingLongPress ? Color.yellow : Color.green)
                .frame(width: 100, height: 100, alignment: .center)
                .gesture(press)
        }
    }
}
```

#### 手势结束时更新永久状态

要识别手势何时成功完成并获取手势的最终值，请使用 [onEnded(_:)](Gesture/onEnded.zh-Hans.md) 函数在回调中更新应用的状态。SwiftUI 仅在手势成功时调用 [onEnded(_:)](Gesture/onEnded.zh-Hans.md) 回调。例如，在 [LongPressGesture](LongPressGesture.zh-Hans.md) 期间，如果用户在 [minimumDuration](LongPressGesture/minimumDuration.zh-Hans.md) 秒内停止触摸视图，或者手指移动超过 [maximumDistance](LongPressGesture/maximumDistance.zh-Hans.md) 个点，SwiftUI 将不会调用 [onEnded(_:)](Gesture/onEnded.zh-Hans.md) 回调。

例如，要在用户完成长按后停止计数长按尝试，请添加 [onEnded(_:)](Gesture/onEnded.zh-Hans.md) 回调并有条件地应用手势修饰符。

```swift
struct CounterView: View {
    @GestureState private var isDetectingLongPress = false
    @State private var totalNumberOfTaps = 0
    @State private var doneCounting = false
    
    var body: some View {
        let press = LongPressGesture(minimumDuration: 1)
            .updating($isDetectingLongPress) { currentState, gestureState, transaction in
                gestureState = currentState
            }.onChanged { _ in
                self.totalNumberOfTaps += 1
            }
            .onEnded { _ in
                self.doneCounting = true
            }
        
        return VStack {
            Text("\(totalNumberOfTaps)")
                .font(.largeTitle)
            
            Circle()
                .fill(doneCounting ? Color.red : isDetectingLongPress ? Color.yellow : Color.green)
                .frame(width: 100, height: 100, alignment: .center)
                .gesture(doneCounting ? nil : press)
        }
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/Adding-Interactivity-with-Gestures
crawled: 2025-12-02T17:40:49Z
---

# Adding interactivity with gestures

**Article**

Use gesture modifiers to add interactivity to your app.

## Overview

Gesture modifiers handle all of the logic needed to process user-input events such as touches, and recognize when those events match a known gesture pattern, such as a long press or rotation. When recognizing a pattern, SwiftUI runs a callback you use to update the state of a view or perform an action.

### Add gesture modifiers to a view

Each gesture you add applies to a specific view in the view hierarchy. To recognize a gesture event on a particular view, create and configure the gesture, and then use the [gesture(_:including:)](View/gesture___including.zh-Hans.md) modifier:

```swift
struct ShapeTapView: View {
    var body: some View {
        let tap = TapGesture()
            .onEnded { _ in
                print("View tapped!")
            }
        
        return Circle()
            .fill(Color.blue)
            .frame(width: 100, height: 100, alignment: .center)
            .gesture(tap)
    }
}
```

### Respond to gesture callbacks

Depending on the callbacks you add to a gesture modifier, SwiftUI reports back to your code whenever the state of the gesture changes. Gesture modifiers offer three ways to receive updates: [updating(_:body:)](Gesture/updating___body.zh-Hans.md), [onChanged(_:)](Gesture/onChanged.zh-Hans.md), and [onEnded(_:)](Gesture/onEnded.zh-Hans.md).

#### Update transient UI state

To update a view as a gesture changes, add a [GestureState](GestureState.zh-Hans.md) property to your view and update it in the [updating(_:body:)](Gesture/updating___body.zh-Hans.md) callback. SwiftUI invokes the updating callback as soon as it recognizes the gesture and whenever the value of the gesture changes. For example, SwiftUI invokes the updating callback as soon as a magnification gesture begins and then again whenever the magnification value changes. SwiftUI doesn’t invoke the updating callback when the user ends or cancels a gesture. Instead, the gesture state property automatically resets its state back to its initial value.

For example, to make a view that changes color while the user performs a long press, add a gesture state property and update it in the updating callback.

```swift
struct CounterView: View {
    @GestureState private var isDetectingLongPress = false
    
    var body: some View {
        let press = LongPressGesture(minimumDuration: 1)
            .updating($isDetectingLongPress) { currentState, gestureState, transaction in
                gestureState = currentState
            }
        
        return Circle()
            .fill(isDetectingLongPress ? Color.yellow : Color.green)
            .frame(width: 100, height: 100, alignment: .center)
            .gesture(press)
    }
}
```

#### Update permanent state during a gesture

To track changes to a gesture that shouldn’t reset once the gesture ends, use the [onChanged(_:)](Gesture/onChanged.zh-Hans.md) callback. For example, to count the number of times your app recognizes a long press, add an [onChanged(_:)](Gesture/onChanged.zh-Hans.md) callback and increment a counter.

```swift
struct CounterView: View {
    @GestureState private var isDetectingLongPress = false
    @State private var totalNumberOfTaps = 0
    
    var body: some View {
        let press = LongPressGesture(minimumDuration: 1)
            .updating($isDetectingLongPress) { currentState, gestureState, transaction in
                gestureState = currentState
            }.onChanged { _ in
                self.totalNumberOfTaps += 1
            }
        
        return VStack {
            Text("\(totalNumberOfTaps)")
                .font(.largeTitle)
            
            Circle()
                .fill(isDetectingLongPress ? Color.yellow : Color.green)
                .frame(width: 100, height: 100, alignment: .center)
                .gesture(press)
        }
    }
}
```

#### Update permanent state when a gesture ends

To recognize when a gesture successfully completes and to retrieve the gesture’s final value, use the [onEnded(_:)](Gesture/onEnded.zh-Hans.md) function to update your app’s state in the callback. SwiftUI only invokes the [onEnded(_:)](Gesture/onEnded.zh-Hans.md) callback when the gesture succeeds. For example, during a [LongPressGesture](LongPressGesture.zh-Hans.md) if the user stops touching the view before [minimumDuration](LongPressGesture/minimumDuration.zh-Hans.md) seconds have elapsed or moves their finger more than [maximumDistance](LongPressGesture/maximumDistance.zh-Hans.md) points SwiftUI does not invoke the [onEnded(_:)](Gesture/onEnded.zh-Hans.md) callback.

For example, to stop counting long press attempts after the user completes a long press, add an [onEnded(_:)](Gesture/onEnded.zh-Hans.md) callback and conditionally apply the gesture modifier.

```swift
struct CounterView: View {
    @GestureState private var isDetectingLongPress = false
    @State private var totalNumberOfTaps = 0
    @State private var doneCounting = false
    
    var body: some View {
        let press = LongPressGesture(minimumDuration: 1)
            .updating($isDetectingLongPress) { currentState, gestureState, transaction in
                gestureState = currentState
            }.onChanged { _ in
                self.totalNumberOfTaps += 1
            }
            .onEnded { _ in
                self.doneCounting = true
            }
        
        return VStack {
            Text("\(totalNumberOfTaps)")
                .font(.largeTitle)
            
            Circle()
                .fill(doneCounting ? Color.red : isDetectingLongPress ? Color.yellow : Color.green)
                .frame(width: 100, height: 100, alignment: .center)
                .gesture(doneCounting ? nil : press)
        }
    }
}
```

