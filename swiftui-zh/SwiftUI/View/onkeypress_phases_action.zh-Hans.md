--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onKeyPress(phases:action:)

抓取时间：2025-12-02T17:41:29Z

---

# onKeyPress(phases:action:)

**实例方法**

当用户在视图获得焦点时按下硬件键盘上的任意键，此方法会执行相应的操作。

## 声明

```swift
nonisolated func onKeyPress(phases: KeyPress.Phases = [.down, .repeat], action: @escaping (KeyPress) -> KeyPress.Result) -> some View

```

## 参数

- **phases**：要匹配的按键阶段（`.down`、`.repeat` 和 `.up`）。默认值为 `[.down, .repeat]`。

- **action**：要执行的操作。该操作接收一个描述匹配按键事件的值。返回 `.handled` 以消耗该事件并阻止进一步分发，或返回 `.ignored` 以允许继续分发。

## 返回值

一个修改后的视图，当视图获得焦点时，该视图会绑定硬件键盘输入。

## 响应键盘输入

- **onKeyPress(_:action:)**：如果用户在视图获得焦点时按下硬件键盘上的某个键，则执行此操作。

- **onKeyPress(_:phases:action:)**：如果用户在视图获得焦点时按下硬件键盘上的某个键，则执行此操作。

- **onKeyPress(characters:phases:action:)**：如果用户在视图获得焦点时按下硬件键盘上的一个或多个键，则执行此操作。

- **onKeyPress(keys:phases:action:)**：如果用户在视图获得焦点时按下硬件键盘上的一个或多个键，则执行此操作。

- **KeyPress**


---
source: https://developer.apple.com/documentation/SwiftUI/View/onKeyPress(phases:action:)
crawled: 2025-12-02T17:41:29Z
---

# onKeyPress(phases:action:)

**Instance Method**

Performs an action if the user presses any key on a hardware keyboard while the view has focus.

## Declaration

```swift
nonisolated func onKeyPress(phases: KeyPress.Phases = [.down, .repeat], action: @escaping (KeyPress) -> KeyPress.Result) -> some View

```

## Parameters

- **phases**: The key-press phases to match (`.down`, `.repeat`, and `.up`). The default value is `[.down, .repeat]`.
- **action**: The action to perform. The action receives a value describing the matched key event. Return `.handled` to consume the event and prevent further dispatch, or `.ignored` to allow dispatch to continue.

## Return Value

A modified view that binds hardware keyboard input when focused.

## Responding to keyboard input

- **onKeyPress(_:action:)**: Performs an action if the user presses a key on a hardware keyboard while the view has focus.
- **onKeyPress(_:phases:action:)**: Performs an action if the user presses a key on a hardware keyboard while the view has focus.
- **onKeyPress(characters:phases:action:)**: Performs an action if the user presses one or more keys on a hardware keyboard while the view has focus.
- **onKeyPress(keys:phases:action:)**: Performs an action if the user presses one or more keys on a hardware keyboard while the view has focus.
- **KeyPress**

