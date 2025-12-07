--- 来源：https://developer.apple.com/documentation/SwiftUI/NSHostingView/keyUp(with:)

抓取时间：2025-12-03T06:51:31Z

---

# keyUp(with:)

**实例方法**

当用户在响应链中松开键盘上的按键时调用。

## 声明

```swift
@MainActor @preconcurrency override dynamic func keyUp(with event: NSEvent)
```

## 管理键盘交互

- **keyDown(with:)**：当用户在响应链中按下键盘上的按键时调用。

- **performKeyEquivalent(with:)**

- **insertText(_:)**

- **didChangeValue(forKey:)**

- **makeTouchBar()**


---
source: https://developer.apple.com/documentation/SwiftUI/NSHostingView/keyUp(with:)
crawled: 2025-12-03T06:51:31Z
---

# keyUp(with:)

**Instance Method**

Called when the user releases a key on the keyboard while this view is in the responder chain.

## Declaration

```swift
@MainActor @preconcurrency override dynamic func keyUp(with event: NSEvent)
```

## Managing keyboard interaction

- **keyDown(with:)**: Called when the user presses a key on the keyboard while this view is in the responder chain.
- **performKeyEquivalent(with:)**
- **insertText(_:)**
- **didChangeValue(forKey:)**
- **makeTouchBar()**

