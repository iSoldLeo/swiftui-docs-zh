---
来源： https://developer.apple.com/documentation/SwiftUI/KeyboardShortcut/defaultAction
抓取时间： 2025-12-03T06:44:37Z
---

# 默认操作

**类型属性**

默认按钮的标准键盘快捷键，由 Return () 键和无修饰符组成。

### 声明

```swift
static let defaultAction: KeyboardShortcut
```

## 讨论

在 macOS 上，默认按钮被指定为特殊颜色。如果有多个控件被指定了此快捷方式，则只有第一个会被强调。

## 获取标准快捷方式

- **cancelAction**：标准键盘快捷键，用于取消正在执行的操作或解除提示，由 Escape (⎋) 键和无修饰符组成。


---
source: https://developer.apple.com/documentation/SwiftUI/KeyboardShortcut/defaultAction
crawled: 2025-12-03T06:44:37Z
---

# defaultAction

**Type Property**

The standard keyboard shortcut for the default button, consisting of the Return (↩) key and no modifiers.

## Declaration

```swift
static let defaultAction: KeyboardShortcut
```

## Discussion

On macOS, the default button is designated with special coloration. If more than one control is assigned this shortcut, only the first one is emphasized.

## Getting standard shortcuts

- **cancelAction**: The standard keyboard shortcut for cancelling the in-progress action or dismissing a prompt, consisting of the Escape (⎋) key and no modifiers.

