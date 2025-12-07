---
来源： https://developer.apple.com/documentation/SwiftUI/KeyboardShortcut/init(_:modifiers:)
抓取时间：2025-12-03T06:44:38Z
---

# init(_:modifiers:)

**Initializer**

使用给定的等效键和修饰符键集创建新的键盘快捷方式。

## 声明

```swift
init(_ key: KeyEquivalent, modifiers: EventModifiers = .command)
```

## 讨论

本地化配置默认为 [automatic](Localization-swift_struct/automatic.zh-Hans.md)。

## 创建快捷方式

- **key**：用户与任何指定的修饰符键一起按下以激活快捷方式的等效键。
- **modifiers**：用户连同等效键一起按下以激活快捷键的修改键。


---
source: https://developer.apple.com/documentation/SwiftUI/KeyboardShortcut/init(_:modifiers:)
crawled: 2025-12-03T06:44:38Z
---

# init(_:modifiers:)

**Initializer**

Creates a new keyboard shortcut with the given key equivalent and set of modifier keys.

## Declaration

```swift
init(_ key: KeyEquivalent, modifiers: EventModifiers = .command)
```

## Discussion

The localization configuration defaults to [automatic](Localization-swift_struct/automatic.zh-Hans.md).

## Creating a shortcut

- **key**: The key equivalent that the user presses in conjunction with any specified modifier keys to activate the shortcut.
- **modifiers**: The modifier keys that the user presses in conjunction with a key equivalent to activate the shortcut.

