--- 来源：https://developer.apple.com/documentation/SwiftUI/TextInputDictationBehavior/automatic
抓取时间：2025-12-04T13:21:47Z

---

# automatic

**类型属性**

适用于特定平台的默认文本输入听写行为。

## 声明

```swift
static let automatic: TextInputDictationBehavior
```

## 讨论

自动行为在 VisionOS 应用中使用 [TextInputDictationActivation](../TextInputDictationActivation.zh-Hans.md) 值 [onLook](../TextInputDictationActivation/onLook.zh-Hans.md)，在 iOS 应用中使用 [onSelect](../TextInputDictationActivation/onSelect.zh-Hans.md)。

## 获取行为值

- **inline(activation:)**：在搜索栏中添加听写麦克风。

- **preventDictation**：禁止在搜索栏中使用听写麦克风。


---
source: https://developer.apple.com/documentation/SwiftUI/TextInputDictationBehavior/automatic
crawled: 2025-12-04T13:21:47Z
---

# automatic

**Type Property**

A platform-appropriate default text input dictation behavior.

## Declaration

```swift
static let automatic: TextInputDictationBehavior
```

## Discussion

The automatic behavior uses a [TextInputDictationActivation](../TextInputDictationActivation.zh-Hans.md) value of [onLook](../TextInputDictationActivation/onLook.zh-Hans.md) for visionOS apps and [onSelect](../TextInputDictationActivation/onSelect.zh-Hans.md) for iOS apps.

## Getting behavior values

- **inline(activation:)**: Adds a dictation microphone in the search bar.
- **preventDictation**: Prevents the search bar from having a dictation microphone.

