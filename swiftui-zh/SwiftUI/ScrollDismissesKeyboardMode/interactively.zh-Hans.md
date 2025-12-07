--- 来源：https://developer.apple.com/documentation/SwiftUI/ScrollDismissesKeyboardMode/interactively
抓取时间：2025-12-03T06:43:10Z

---

# interactively

**类型属性**

允许用户在滚动操作过程中交互式地关闭键盘。

## 声明

```swift
static var interactively: ScrollDismissesKeyboardMode { get }
```

## 讨论

如果滚动操作的手势进入键盘所在的屏幕区域，软件键盘的位置会跟随该手势移动。用户可以通过滚动将键盘移出屏幕来关闭键盘，或者反向滚动来取消关闭操作。

## 获取模式

- **automatic**：根据上下文自动确定模式。

- **immediately**：滚动开始时立即关闭键盘。

- **never**：滚动页面时，键盘不应自动关闭。


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollDismissesKeyboardMode/interactively
crawled: 2025-12-03T06:43:10Z
---

# interactively

**Type Property**

Enable people to interactively dismiss the keyboard as part of the scroll operation.

## Declaration

```swift
static var interactively: ScrollDismissesKeyboardMode { get }
```

## Discussion

The software keyboard’s position tracks the gesture that drives the scroll operation if the gesture crosses into the keyboard’s area of the display. People can dismiss the keyboard by scrolling it off the display, or reverse the direction of the scroll to cancel the dismissal.

## Getting modes

- **automatic**: Determine the mode automatically based on the surrounding context.
- **immediately**: Dismiss the keyboard as soon as scrolling starts.
- **never**: Never dismiss the keyboard automatically as a result of scrolling.

