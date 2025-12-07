--- 来源：https://developer.apple.com/documentation/SwiftUI/AccessibilityDirectTouchOptions/requiresActivation
抓取时间：2025-12-03T06:49:10Z

---

# requiresActivation

**类型属性**

阻止直接触摸区域在辅助技术（例如 VoiceOver）通过用户操作（例如双击）激活之前进行触摸传递。

## 声明

```swift
static let requiresActivation: AccessibilityDirectTouchOptions
```

## 获取选项

- **silentOnTouch**：允许直接触摸区域在辅助技术（例如 VoiceOver）未发声的情况下立即接收触摸事件。适用于提供直接触摸音频反馈且该反馈会与语音反馈冲突的应用。


---
source: https://developer.apple.com/documentation/SwiftUI/AccessibilityDirectTouchOptions/requiresActivation
crawled: 2025-12-03T06:49:10Z
---

# requiresActivation

**Type Property**

Prevents touch passthrough with the direct touch area until an assistive technology, such as VoiceOver, has activated the direct touch area through a user action, for example a double tap.

## Declaration

```swift
static let requiresActivation: AccessibilityDirectTouchOptions
```

## Getting the options

- **silentOnTouch**: Allows a direct touch area to immediately receive touch events without an assitive technology, such as VoiceOver, speaking. Appropriate for apps that provide direct audio feedback on touch that would conflict with speech feedback.

