--- 来源：https://developer.apple.com/documentation/SwiftUI/AccessibilityDirectTouchOptions/silentOnTouch

抓取时间：2025-12-03T06:49:11Z

---

# silentOnTouch

**类型属性**

允许直接触摸区域在辅助技术（例如 VoiceOver）发出语音之前立即接收触摸事件。适用于提供直接触摸音频反馈且可能与语音反馈冲突的应用。

## 声明

```swift
static let silentOnTouch: AccessibilityDirectTouchOptions
```

## 获取选项

- **requiresActivation**：阻止直接触摸区域的触摸穿透，直到辅助技术（例如 VoiceOver）通过用户操作（例如双击）激活直接触摸区域。


---
source: https://developer.apple.com/documentation/SwiftUI/AccessibilityDirectTouchOptions/silentOnTouch
crawled: 2025-12-03T06:49:11Z
---

# silentOnTouch

**Type Property**

Allows a direct touch area to immediately receive touch events without an assitive technology, such as VoiceOver, speaking. Appropriate for apps that provide direct audio feedback on touch that would conflict with speech feedback.

## Declaration

```swift
static let silentOnTouch: AccessibilityDirectTouchOptions
```

## Getting the options

- **requiresActivation**: Prevents touch passthrough with the direct touch area until an assistive technology, such as VoiceOver, has activated the direct touch area through a user action, for example a double tap.

