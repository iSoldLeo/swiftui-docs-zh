--- 来源：https://developer.apple.com/documentation/SwiftUI/ScrollDismissesKeyboardMode/automatic

抓取时间：2025-12-03T06:43:09Z

---

# automatic

**Type 属性**

根据上下文自动确定键盘模式。

## 声明

```swift
static var automatic: ScrollDismissesKeyboardMode { get }
```

## 讨论

默认情况下，[TextEditor](../TextEditor.zh-Hans.md) 是交互式的，而 [List](../List.zh-Hans.md) 是可滚动内容，在 iOS 16 或更高版本中，滚动时键盘始终会关闭。

## 获取模式

- **immediately**：滚动开始时立即关闭键盘。

- **interactively**：允许用户在滚动操作过程中以交互方式关闭键盘。

- **never**：滚动页面时，键盘不应自动关闭。


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollDismissesKeyboardMode/automatic
crawled: 2025-12-03T06:43:09Z
---

# automatic

**Type Property**

Determine the mode automatically based on the surrounding context.

## Declaration

```swift
static var automatic: ScrollDismissesKeyboardMode { get }
```

## Discussion

By default, a [TextEditor](../TextEditor.zh-Hans.md) is interactive while a [List](../List.zh-Hans.md) of scrollable content always dismiss the keyboard on a scroll, when linked against iOS 16 or later.

## Getting modes

- **immediately**: Dismiss the keyboard as soon as scrolling starts.
- **interactively**: Enable people to interactively dismiss the keyboard as part of the scroll operation.
- **never**: Never dismiss the keyboard automatically as a result of scrolling.

