--- 来源：https://developer.apple.com/documentation/SwiftUI/NSHostingView/keyDown(with:)

抓取时间：2025-12-01T11:40:42Z

---

# keyDown(with:)

**实例方法**

当用户按下键盘上的某个键，且此视图处于响应链中时，将调用此方法。

## 声明

```swift
@MainActor @preconcurrency override dynamic func keyDown(with event: NSEvent)
```

## 管理键盘交互

- **keyUp(with:)**：当用户松开键盘上的某个键，且此视图处于响应链中时，将调用此方法。

- **performKeyEquivalent(with:)**

- **insertText(_:)**

- **didChangeValue(forKey:)**

- **makeTouchBar()**


---
source: https://developer.apple.com/documentation/SwiftUI/NSHostingView/keyDown(with:)
crawled: 2025-12-01T11:40:42Z
---

# keyDown(with:)

**Instance Method**

Called when the user presses a key on the keyboard while this view is in the responder chain.

## Declaration

```swift
@MainActor @preconcurrency override dynamic func keyDown(with event: NSEvent)
```

## Managing keyboard interaction

- **keyUp(with:)**: Called when the user releases a key on the keyboard while this view is in the responder chain.
- **performKeyEquivalent(with:)**
- **insertText(_:)**
- **didChangeValue(forKey:)**
- **makeTouchBar()**

