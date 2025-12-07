--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onModifierKeysChanged(mask:initial:_:)

抓取时间：2025-11-30T21:26:48Z

---

# onModifierKeysChanged(mask:initial:_:)

**实例方法**

当用户按下或释放硬件修饰键时，执行相应的操作。

## 声明

```swift
nonisolated func onModifierKeysChanged(mask: EventModifiers = .all, initial: Bool = true, _ action: @escaping (EventModifiers, EventModifiers) -> Void) -> some View

```

## 参数

- **mask**：一组修饰键，用于控制要监听哪些键的变化。默认掩码包含所有键。

- **action**：一个闭包，用于接收修饰键按下状态变化时的更新。该闭包接收旧值和新值作为输入。

## 返回值

一个在硬件修饰键变化时更新的视图。

## 讨论

如果提供了掩码，则只有当掩码中包含的某个键发生变化时才会进行更新。默认掩码包含所有修饰键。

```swift
ContentView()
    .onModifierKeysChanged(mask: .option) { old, new in
        if new.isEmpty {
            // Option key released
            ...
        } else {
            // Option key pressed
            ...
        }
    }
```

视图首次出现时，SwiftUI 会检查修饰键的状态，如果按下了任何匹配的键，则会调用提供的操作。否则，第一次调用会在用户首次按下匹配的修饰键时触发。当同时使用多个键盘时，流发出的更新会反映所有已连接键盘上所有被按下的修饰键的组合。

## 响应修饰键

- **modifierKeyAlternate(_:_:)**：构建一个视图，当用户按下给定集合中指示的修饰键时，该视图将替换为已修改的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/View/onModifierKeysChanged(mask:initial:_:)
crawled: 2025-11-30T21:26:48Z
---

# onModifierKeysChanged(mask:initial:_:)

**Instance Method**

Performs an action whenever the user presses or releases a hardware modifier key.

## Declaration

```swift
nonisolated func onModifierKeysChanged(mask: EventModifiers = .all, initial: Bool = true, _ action: @escaping (EventModifiers, EventModifiers) -> Void) -> some View

```

## Parameters

- **mask**: A set of modifier keys controlling which keys to observe for changes. The default mask includes all keys.
- **action**: A closure to receive updates when modifier key press state changes. The closure receives the old and new values as input.

## Return Value

A modified view that updates when hardware modifier keys change.

## Discussion

If a mask is provided, updates will only occur when they involve a change in one of the keys included in the mask. The default mask includes all modifier keys.

```swift
ContentView()
    .onModifierKeysChanged(mask: .option) { old, new in
        if new.isEmpty {
            // Option key released
            ...
        } else {
            // Option key pressed
            ...
        }
    }
```

When the view first appears, SwiftUI will check the state of the modifier keys and call the provided action if any matched keys are pressed. Otherwise, the first call will come the first time the user presses a matched modifier key down. When multiple keyboards are in use at the same time, the updates emitted by the stream reflect the combined set of all modifier keys being held down on all attached keyboards.

## Responding to modifier keys

- **modifierKeyAlternate(_:_:)**: Builds a view to use in place of the modified view when the user presses the modifier key(s) indicated by the given set.

