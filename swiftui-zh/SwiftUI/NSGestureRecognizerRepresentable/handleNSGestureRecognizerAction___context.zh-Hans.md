--- 来源：https://developer.apple.com/documentation/SwiftUI/NSGestureRecognizerRepresentable/handleNSGestureRecognizerAction(_:context:)

抓取时间：2025-12-03T06:58:02Z

---

# handleNSGestureRecognizerAction(_:context:)

**实例方法**

处理所代表手势的识别。

## 声明

```swift
@MainActor @preconcurrency func handleNSGestureRecognizerAction(_ recognizer: Self.NSGestureRecognizerType, context: Self.Context)
```

## 参数

- **recognizer**：所代表手势识别器的实例。

- **context**：包含系统当前状态信息的上下文结构，例如当前协调器实例。

## 讨论

如果您实现了此方法，SwiftUI 会在识别到封装的手势识别器时调用它。


---
source: https://developer.apple.com/documentation/SwiftUI/NSGestureRecognizerRepresentable/handleNSGestureRecognizerAction(_:context:)
crawled: 2025-12-03T06:58:02Z
---

# handleNSGestureRecognizerAction(_:context:)

**Instance Method**

Handles recognition of the represented `NSGestureRecognizer`.

## Declaration

```swift
@MainActor @preconcurrency func handleNSGestureRecognizerAction(_ recognizer: Self.NSGestureRecognizerType, context: Self.Context)
```

## Parameters

- **recognizer**: An instance of the represented gesture recognizer.
- **context**: A context structure containing information about the current state of the system, such as the current coordinator instance.

## Discussion

If you implement this method, SwiftUI calls it when the wrapped gesture recognizer is recognized.

