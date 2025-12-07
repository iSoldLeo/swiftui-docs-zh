--- 来源：https://developer.apple.com/documentation/SwiftUI/Gesture/handActivationBehavior(_:)

抓取时间：2025-12-03T06:44:10Z

---

# handActivationBehavior(_:)

**实例方法**

自定义手势在由手或类似手的输入驱动时的激活行为。

## 声明

```swift
@MainActor @preconcurrency func handActivationBehavior(_ behavior: HandActivationBehavior) -> some Gesture<Self.Value>

```

## 参数

- **behavior**：用于手势的手部激活行为。

## 返回值

一个新手势，并指定使用提供的行为进行激活。

## 说明

使用 [automatic](../HandActivationBehavior/automatic.zh-Hans.md) 允许手势使用默认系统行为激活。使用 [pinch](../HandActivationBehavior/pinch.zh-Hans.md) 仅当手部捏合时才应触发手势。

例如，在 3D 国际象棋应用中，用于控制棋子移动的 [DragGesture](../DragGesture.zh-Hans.md) 可以使用捏合动作来确保只有在手部捏合时才能移动棋子，从而避免仅通过触摸来推动棋子：

```swift
Model3D(named: "Pawn")
    .gesture(
        DragGesture()
            .handActivationBehavior(.pinch)
            .updating($chessDragState) { value, state, _ in
                // ...
            }
    )
```


---
source: https://developer.apple.com/documentation/SwiftUI/Gesture/handActivationBehavior(_:)
crawled: 2025-12-03T06:44:10Z
---

# handActivationBehavior(_:)

**Instance Method**

Customizes the activation behavior for a gesture when driven by hand or hand-like input.

## Declaration

```swift
@MainActor @preconcurrency func handActivationBehavior(_ behavior: HandActivationBehavior) -> some Gesture<Self.Value>

```

## Parameters

- **behavior**: The hand activation behavior to use for the gesture.

## Return Value

A new gesture with a preference to activate with the provided behavior.

## Discussion

Use [automatic](../HandActivationBehavior/automatic.zh-Hans.md) to allow a gesture to activate with default system behaviors. Use [pinch](../HandActivationBehavior/pinch.zh-Hans.md) when a gesture should only trigger when the hand is pinched.

For example, in a 3D chess application, a [DragGesture](../DragGesture.zh-Hans.md) that enables movement of the pieces could use the pinch behavior to ensure that piece movement is only possible when a hand is pinched in order to avoid pushing the piece around by only touching it:

```swift
Model3D(named: "Pawn")
    .gesture(
        DragGesture()
            .handActivationBehavior(.pinch)
            .updating($chessDragState) { value, state, _ in
                // ...
            }
    )
```

