---
来源： https://developer.apple.com/documentation/SwiftUI/KeyboardShortcut/Localization-swift.struct
抓取时间： 2025-12-03T06:44:42Z
---

# 键盘快捷键本地化

**Structure**

键盘快捷方式如何参与自动本地化的选项。

## 声明

```swift
struct Localization
```

## 概览

在美英键盘布局上定义的快捷键`key` 在国际键盘布局上可能无法使用。例如，快捷键`⌘[` 在美式键盘布局中很好用，但在德式键盘布局中却难以使用。在德文键盘布局中，按 `⌥5` 会产生 `[`，从而使快捷键变为 `⌥⌘5`。如果配置了（这是默认行为），自动快捷方式重映射会将其转换为 `⌘Ö`。

除此之外，某些键盘快捷键还带有方向性信息。右对齐文本块或在播放音乐时向前搜索就是这样的例子。这类快捷键可以使用[withoutMirroring](Localization-swift_struct/withoutMirroring.zh-Hans.md)选项来告诉系统，在从右到左的上下文中运行时，它们不会被翻转。

## 获取本地化策略

- **automatic**：将快捷方式重新映射为国际对应快捷方式，并在适当情况下镜像为从右向左的使用方式。
- **custom**：不使用自动快捷方式重映射。
- **withoutMirroring**：不要镜像快捷方式。

## 创建本地化快捷方式

- **init(_:modifiers:localization:)**：用给定的等效键和一组修改键创建新的快捷键。
- **localization**：应用于此快捷方式的本地化策略。

## 符合

- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/KeyboardShortcut/Localization-swift.struct
crawled: 2025-12-03T06:44:42Z
---

# KeyboardShortcut.Localization

**Structure**

Options for how a keyboard shortcut participates in automatic localization.

## Declaration

```swift
struct Localization
```

## Overview

A shortcut’s `key` that is defined on an US-English keyboard layout might not be reachable on international layouts. For example the shortcut `⌘[` works well for the US layout but is hard to reach for German users. On the German keyboard layout, pressing `⌥5` will produce `[`, which causes the shortcut to become `⌥⌘5`. If configured, which is the default behavior, automatic shortcut remapping will convert it to `⌘Ö`.

In addition to that, some keyboard shortcuts carry information about directionality. Right-aligning a block of text or seeking forward in context of music playback are such examples. These kinds of shortcuts benefit from the option [withoutMirroring](Localization-swift_struct/withoutMirroring.zh-Hans.md) to tell the system that they won’t be flipped when running in a right-to-left context.

## Getting localization strategies

- **automatic**: Remap shortcuts to their international counterparts, mirrored for right-to-left usage if appropriate.
- **custom**: Don’t use automatic shortcut remapping.
- **withoutMirroring**: Don’t mirror shortcuts.

## Creating a localized shortcut

- **init(_:modifiers:localization:)**: Creates a new keyboard shortcut with the given key equivalent and set of modifier keys.
- **localization**: The localization strategy to apply to this shortcut.

## Conforms To

- Sendable
- SendableMetatype

