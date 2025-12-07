--- 来源：https://developer.apple.com/documentation/SwiftUI/EventModifiers
抓取时间：2025-12-02T17:41:44Z

---

# 事件修饰符

**Structure**

一组可以添加到手势中的按键修饰符。

## 声明

```swift
@frozen struct EventModifiers
```

## 获取修饰键

- **all**：所有可能的修饰键。

- **capsLock**：大写锁定键。

- **command**：Command 键。

- **control**：Control 键。

- **numericPad**：数字小键盘上的任意键。

- **option**：Option 键。

- **shift**：Shift 键。

## 创建选项集

- **init(rawValue:)**：从原始值创建新的选项集。

- **rawValue**：原始值。

## 已弃用的修饰键

- **function**：Fn 键。

## 创建键盘快捷键

- **keyboardShortcut(_:)**：为修改后的控件分配键盘快捷键。

- **keyboardShortcut(_:modifiers:)**：定义键盘快捷键并将其分配给修改后的控件。

- **keyboardShortcut(_:modifiers:localization:)**：定义键盘快捷键并将其分配给修改后的控件。

- **keyboardShortcut**：此环境中按钮触发所用的键盘快捷键。

- **KeyboardShortcut**：键盘快捷键描述了用户按下键盘上用于激活按钮或切换开关的按键组合。

- **KeyEquivalent**：按键等效项由字母、标点符号或功能键组成，可以与一组可选的修饰键组合使用，以指定键盘快捷键。

## 符合以下规范

- BitwiseCopyable

- Copyable

- Equatable

- ExpressibleByArrayLiteral

- OptionSet

- RawRepresentable

- Sendable

- SendableMetatype

- SetAlgebra


---
source: https://developer.apple.com/documentation/SwiftUI/EventModifiers
crawled: 2025-12-02T17:41:44Z
---

# EventModifiers

**Structure**

A set of key modifiers that you can add to a gesture.

## Declaration

```swift
@frozen struct EventModifiers
```

## Getting modifier keys

- **all**: All possible modifier keys.
- **capsLock**: The Caps Lock key.
- **command**: The Command key.
- **control**: The Control key.
- **numericPad**: Any key on the numeric keypad.
- **option**: The Option key.
- **shift**: The Shift key.

## Creating a set of options

- **init(rawValue:)**: Creates a new set from a raw value.
- **rawValue**: The raw value.

## Deprecated modifiers

- **function**: The Function key.

## Creating keyboard shortcuts

- **keyboardShortcut(_:)**: Assigns a keyboard shortcut to the modified control.
- **keyboardShortcut(_:modifiers:)**: Defines a keyboard shortcut and assigns it to the modified control.
- **keyboardShortcut(_:modifiers:localization:)**: Defines a keyboard shortcut and assigns it to the modified control.
- **keyboardShortcut**: The keyboard shortcut that buttons in this environment will be triggered with.
- **KeyboardShortcut**: Keyboard shortcuts describe combinations of keys on a keyboard that the user can press in order to activate a button or toggle.
- **KeyEquivalent**: Key equivalents consist of a letter, punctuation, or function key that can be combined with an optional set of modifier keys to specify a keyboard shortcut.

## Conforms To

- BitwiseCopyable
- Copyable
- Equatable
- ExpressibleByArrayLiteral
- OptionSet
- RawRepresentable
- Sendable
- SendableMetatype
- SetAlgebra

