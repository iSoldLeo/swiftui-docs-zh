---
来源： https://developer.apple.com/documentation/SwiftUI/KeyboardShortcut/init(_:modifiers:localization:)
抓取时间：2025-12-03T06:44:40Z
---

# init(_:modifiers:localization:)

**Initializer**

使用给定的等效键和修饰符键集创建新的键盘快捷方式。

## 声明

```swift
init(_ key: KeyEquivalent, modifiers: EventModifiers = .command, localization: KeyboardShortcut.Localization)
```

## 讨论

使用 `localization` 参数为该快捷方式指定本地化策略。

## 创建本地化快捷方式

- **localization**：要应用于此快捷方式的本地化策略。
- **KeyboardShortcut.Localization**：键盘快捷方式如何参与自动本地化的选项。


---
source: https://developer.apple.com/documentation/SwiftUI/KeyboardShortcut/init(_:modifiers:localization:)
crawled: 2025-12-03T06:44:40Z
---

# init(_:modifiers:localization:)

**Initializer**

Creates a new keyboard shortcut with the given key equivalent and set of modifier keys.

## Declaration

```swift
init(_ key: KeyEquivalent, modifiers: EventModifiers = .command, localization: KeyboardShortcut.Localization)
```

## Discussion

Use the `localization` parameter to specify a localization strategy for this shortcut.

## Creating a localized shortcut

- **localization**: The localization strategy to apply to this shortcut.
- **KeyboardShortcut.Localization**: Options for how a keyboard shortcut participates in automatic localization.

