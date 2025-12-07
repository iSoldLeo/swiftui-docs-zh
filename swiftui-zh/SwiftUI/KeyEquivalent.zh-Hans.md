---
来源： https://developer.apple.com/documentation/SwiftUI/KeyEquivalent
抓取时间： 2025-12-02T17:41:43Z
---

# KeyEquivalent

**Structure**

等效键由字母、标点符号或功能键组成，可与一组可选的修改键组合，指定键盘快捷键。

### 声明

```swift
struct KeyEquivalent
```

## 概览

等效键用于建立应用程序功能的键盘快捷方式。任何按键都可用作等效键，只要按下后会产生一个字符值。按键等效通常使用单字符字符串字面进行初始化，并为无法打印或难以输入的值提供常量。

键入等效键所需的修改键会被计入生成的键盘快捷方式中。例如，原始值为大写字符串 "A "的等价键对应于键盘快捷键 Command-Shift-A。确切的映射可能取决于键盘布局--例如，在 ANSI 键盘上，字符值为"}"的等效键产生的快捷键相当于 Command-Shift-]，但在标点符号位于不同位置的键盘布局上，则会产生不同的快捷键。

### 获取箭头键

- **upArrow**：向上箭头 (U+F700)
- **downArrow**：向下箭头 (U+F701)
- **leftArrow**：左箭头 (U+F702)
- **rightArrow**：右箭头 (U+F703)

## 获取其他特殊按键

- **clear**：清除 (U+F739)
- **delete**：删除 (U+0008)
- **deleteForward**：向前删除 (U+F728)
- **end**：结束 (U+F72B)
- **escape**：Escape (U+001B)
- **home**：主页 (U+F729)
- **pageDown**: 主页 (U+F729)向下翻页 (U+F72D)
- **pageUp**：向上翻页 (U+F72C)
- **return**：返回 (U+000D)
- **space**：空格 (U+0020)
- **tab**: 空格 (U+0020)制表符 (U+0009)

## 创建等价键

- **init(_:)**：根据给定的字符值创建新的等价键。
- **character**：键等价所代表的字符值。

### 创建键盘快捷方式

- **keyboardShortcut(_:)**：为修改后的控件指定键盘快捷键。
- **keyboardShortcut(_:modifiers:)**：定义键盘快捷键并将其分配给修改后的控件。
- **keyboardShortcut(_:modifiers:localization:)**：定义键盘快捷键并将其分配给修改后的控件。
- **keyboardShortcut**：在此环境中触发按钮的键盘快捷键。
- **KeyboardShortcut**：键盘快捷键描述了用户可以按下键盘上的组合键来激活按钮或切换键。
- **EventModifiers**：可以添加到手势中的一组按键修饰符。

## 符合

- 可复制
- 可等同
- 可通过扩展音节集表达
- 可通过UnicodeScalarLiteral表达
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/KeyEquivalent
crawled: 2025-12-02T17:41:43Z
---

# KeyEquivalent

**Structure**

Key equivalents consist of a letter, punctuation, or function key that can be combined with an optional set of modifier keys to specify a keyboard shortcut.

## Declaration

```swift
struct KeyEquivalent
```

## Overview

Key equivalents are used to establish keyboard shortcuts to app functionality. Any key can be used as a key equivalent as long as pressing it produces a single character value. Key equivalents are typically initialized using a single-character string literal, with constants for unprintable or hard-to-type values.

The modifier keys necessary to type a key equivalent are factored in to the resulting keyboard shortcut. That is, a key equivalent whose raw value is the capitalized string “A” corresponds with the keyboard shortcut Command-Shift-A. The exact mapping may depend on the keyboard layout—for example, a key equivalent with the character value “}” produces a shortcut equivalent to Command-Shift-] on ANSI keyboards, but would produce a different shortcut for keyboard layouts where punctuation characters are in different locations.

## Getting arrow keys

- **upArrow**: Up Arrow (U+F700)
- **downArrow**: Down Arrow (U+F701)
- **leftArrow**: Left Arrow (U+F702)
- **rightArrow**: Right Arrow (U+F703)

## Getting other special keys

- **clear**: Clear (U+F739)
- **delete**: Delete (U+0008)
- **deleteForward**: Delete Forward (U+F728)
- **end**: End (U+F72B)
- **escape**: Escape (U+001B)
- **home**: Home (U+F729)
- **pageDown**: Page Down (U+F72D)
- **pageUp**: Page Up (U+F72C)
- **return**: Return (U+000D)
- **space**: Space (U+0020)
- **tab**: Tab (U+0009)

## Creating a key equivalent

- **init(_:)**: Creates a new key equivalent from the given character value.
- **character**: The character value that the key equivalent represents.

## Creating keyboard shortcuts

- **keyboardShortcut(_:)**: Assigns a keyboard shortcut to the modified control.
- **keyboardShortcut(_:modifiers:)**: Defines a keyboard shortcut and assigns it to the modified control.
- **keyboardShortcut(_:modifiers:localization:)**: Defines a keyboard shortcut and assigns it to the modified control.
- **keyboardShortcut**: The keyboard shortcut that buttons in this environment will be triggered with.
- **KeyboardShortcut**: Keyboard shortcuts describe combinations of keys on a keyboard that the user can press in order to activate a button or toggle.
- **EventModifiers**: A set of key modifiers that you can add to a gesture.

## Conforms To

- Copyable
- Equatable
- ExpressibleByExtendedGraphemeClusterLiteral
- ExpressibleByUnicodeScalarLiteral
- Hashable
- Sendable
- SendableMetatype

