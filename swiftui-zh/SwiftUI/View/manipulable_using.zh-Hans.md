--- 来源：https://developer.apple.com/documentation/SwiftUI/View/manipulable(using:)

抓取时间：2025-11-30T21:09:38Z

---

# manipulable(using:)

**实例方法**

允许使用附加到其他视图的操作手势来操作当前视图。

## 声明

```swift
nonisolated func manipulable(using gestureState: Manipulable.GestureState) -> some View

```

## 参数

- **gestureState**：由附加到其他视图的操作手势更新的操作手势状态。

## 返回值

一个可以通过附加到其他视图的操作手势来操作的视图。

## 说明

当您希望允许用户通过与另一个视图交互来操作当前视图时，请将此视图修饰符与 [manipulationGesture(updating:coordinateSpace:operations:inertia:isEnabled:onChanged:)](manipulationGesture_updating_coordinateSpace_operations_inertia_isEnabled_onChanged.zh-Hans.md) 一起使用。

在以下示例中，一个人可以做出一个与一副扑克牌相关的操控手势，该手势可以操控单张牌，而不是整副牌：

```swift
struct CardDeck: View {
    @State private var manipulationState = Manipulable.GestureState()

    var body: some View {
        ZStack {
            Model3D(named: "CardDeck")
                .manipulationGesture(updating: $manipulationState)
            Model3D(named: "Card")
                .manipulable(using: manipulationState)
                .opacity(manipulationState.isActive ? 1 : 0)
        }
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/View/manipulable(using:)
crawled: 2025-11-30T21:09:38Z
---

# manipulable(using:)

**Instance Method**

Allows the view to be manipulated using a manipulation gesture attached to a different view.

## Declaration

```swift
nonisolated func manipulable(using gestureState: Manipulable.GestureState) -> some View

```

## Parameters

- **gestureState**: The manipulation gesture state that’s updated by a manipulation gesture added to a different view.

## Return Value

A view that can be manipulated by a manipulation gesture attached to a different view.

## Discussion

Use this view modifier alongside [manipulationGesture(updating:coordinateSpace:operations:inertia:isEnabled:onChanged:)](manipulationGesture_updating_coordinateSpace_operations_inertia_isEnabled_onChanged.zh-Hans.md) when you want to allow a person to manipulate a view by interacting with a different view.

In the following example, a person can begin a manipulation gesture attached to a deck of cards which, in turn, manipulates a single card instead of the entire deck:

```swift
struct CardDeck: View {
    @State private var manipulationState = Manipulable.GestureState()

    var body: some View {
        ZStack {
            Model3D(named: "CardDeck")
                .manipulationGesture(updating: $manipulationState)
            Model3D(named: "Card")
                .manipulable(using: manipulationState)
                .opacity(manipulationState.isActive ? 1 : 0)
        }
    }
}
```



