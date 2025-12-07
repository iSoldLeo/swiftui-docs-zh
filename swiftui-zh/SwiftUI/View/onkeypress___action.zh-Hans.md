--- 来源：https://developer.apple.com/documentation/swiftui/view/onkeypress(_:action:)

抓取时间：2025-12-01T11:33:50Z

---

# onKeyPress(_:action:)

**实例方法**

当用户在视图获得焦点时按下硬件键盘上的某个键，此方法会执行相应的操作。

## 声明

```swift
nonisolated func onKeyPress(_ key: KeyEquivalent, action: @escaping () -> KeyPress.Result) -> some View

```

## 参数

- **key**：要匹配的硬件键盘事件对应的键。

- **action**：要执行的操作。返回 `.handled` 表示消耗该事件并阻止进一步分发，或返回 `.ignored` 表示允许继续分发。

## 返回值

一个在获得焦点时绑定硬件键盘输入的修改后的视图。

## 讨论

SwiftUI 会处理按键按下和按键重复事件。

## 响应键盘输入

- **onKeyPress(phases:action:)**：当用户在视图获得焦点时按下硬件键盘上的任意键，则执行相应的操作。

- **onKeyPress(_:phases:action:)**：当用户在视图获得焦点时按下硬件键盘上的一个键，则执行相应的操作。

- **onKeyPress(characters:phases:action:)**：当用户在视图获得焦点时按下硬件键盘上的一个或多个键，则执行相应的操作。

- **onKeyPress(keys:phases:action:)**：当用户在视图获得焦点时按下硬件键盘上的一个或多个键，则执行相应的操作。

- **KeyPress**


---
source: https://developer.apple.com/documentation/swiftui/view/onkeypress(_:action:)
crawled: 2025-12-01T11:33:50Z
---

# onKeyPress(_:action:)

**Instance Method**

Performs an action if the user presses a key on a hardware keyboard while the view has focus.

## Declaration

```swift
nonisolated func onKeyPress(_ key: KeyEquivalent, action: @escaping () -> KeyPress.Result) -> some View

```

## Parameters

- **key**: The key to match against incoming hardware keyboard events.
- **action**: The action to perform. Return `.handled` to consume the event and prevent further dispatch, or `.ignored` to allow dispatch to continue.

## Return Value

A modified view that binds hardware keyboard input when focused.

## Discussion

SwiftUI performs the action for key-down and key-repeat events.

## Responding to keyboard input

- **onKeyPress(phases:action:)**: Performs an action if the user presses any key on a hardware keyboard while the view has focus.
- **onKeyPress(_:phases:action:)**: Performs an action if the user presses a key on a hardware keyboard while the view has focus.
- **onKeyPress(characters:phases:action:)**: Performs an action if the user presses one or more keys on a hardware keyboard while the view has focus.
- **onKeyPress(keys:phases:action:)**: Performs an action if the user presses one or more keys on a hardware keyboard while the view has focus.
- **KeyPress**

