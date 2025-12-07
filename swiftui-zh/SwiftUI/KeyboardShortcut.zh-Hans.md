--- 来源：https://developer.apple.com/documentation/SwiftUI/KeyboardShortcut

抓取时间：2025-12-02T17:41:42Z

---

# KeyboardShortcut

**Structure**

键盘快捷键描述了用户可以通过按下键盘上的组合键来激活按钮或切换开关。

## 声明

```swift
struct KeyboardShortcut
```

## 获取标准快捷键

- **cancelAction**：用于取消正在进行的操作或关闭提示的标准键盘快捷键，即 Esc 键 (⎋)，不带任何修饰键。

- **defaultAction**：用于默认按钮的标准键盘快捷键，即 Return 键 (↩)，不带任何修饰键。

## 创建快捷键

- **init(_:modifiers:)**：使用指定的按键和修饰键创建一个新的键盘快捷键。

- **key**：用户按下的按键（需配合指定的修饰键）以激活快捷键。

- **modifiers**：用户按下的修饰键（需配合指定的按键）以激活快捷键。

## 创建本地化快捷键

- **init(_:modifiers:localization:)**：使用指定的按键和修饰键创建一个新的键盘快捷键。

- **localization**：应用于此快捷键的本地化策略。

- **KeyboardShortcut.Localization**：键盘快捷键参与自动本地化的选项。

## 创建键盘快捷键

- **keyboardShortcut(_:)**：为修改后的控件分配键盘快捷键。

- **keyboardShortcut(_:modifiers:)**：定义键盘快捷键并将其分配给修改后的控件。

- **keyboardShortcut(_:modifiers:localization:)**：定义键盘快捷键并将其分配给修改后的控件。

- **keyboardShortcut**：此环境中按钮的触发快捷键。

- **KeyEquivalent**：按键等效项由字母、标点符号或功能键组成，可以与一组可选的修饰键组合使用，以指定键盘快捷键。

- **EventModifiers**：可以添加到手势的一组修饰键。

## 符合以下规范

- 可复制

- 可等效

- 可哈希

- 可发送

- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/KeyboardShortcut
crawled: 2025-12-02T17:41:42Z
---

# KeyboardShortcut

**Structure**

Keyboard shortcuts describe combinations of keys on a keyboard that the user can press in order to activate a button or toggle.

## Declaration

```swift
struct KeyboardShortcut
```

## Getting standard shortcuts

- **cancelAction**: The standard keyboard shortcut for cancelling the in-progress action or dismissing a prompt, consisting of the Escape (⎋) key and no modifiers.
- **defaultAction**: The standard keyboard shortcut for the default button, consisting of the Return (↩) key and no modifiers.

## Creating a shortcut

- **init(_:modifiers:)**: Creates a new keyboard shortcut with the given key equivalent and set of modifier keys.
- **key**: The key equivalent that the user presses in conjunction with any specified modifier keys to activate the shortcut.
- **modifiers**: The modifier keys that the user presses in conjunction with a key equivalent to activate the shortcut.

## Creating a localized shortcut

- **init(_:modifiers:localization:)**: Creates a new keyboard shortcut with the given key equivalent and set of modifier keys.
- **localization**: The localization strategy to apply to this shortcut.
- **KeyboardShortcut.Localization**: Options for how a keyboard shortcut participates in automatic localization.

## Creating keyboard shortcuts

- **keyboardShortcut(_:)**: Assigns a keyboard shortcut to the modified control.
- **keyboardShortcut(_:modifiers:)**: Defines a keyboard shortcut and assigns it to the modified control.
- **keyboardShortcut(_:modifiers:localization:)**: Defines a keyboard shortcut and assigns it to the modified control.
- **keyboardShortcut**: The keyboard shortcut that buttons in this environment will be triggered with.
- **KeyEquivalent**: Key equivalents consist of a letter, punctuation, or function key that can be combined with an optional set of modifier keys to specify a keyboard shortcut.
- **EventModifiers**: A set of key modifiers that you can add to a gesture.

## Conforms To

- Copyable
- Equatable
- Hashable
- Sendable
- SendableMetatype

