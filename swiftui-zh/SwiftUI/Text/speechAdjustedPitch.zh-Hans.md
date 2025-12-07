--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/speechAdjustedPitch(_:)

抓取时间：2025-12-01T02:39:28Z

---

# speechAdjustedPitch(_:)

**实例方法**

提高或降低语音文本的音调。

## 声明

```swift
func speechAdjustedPitch(_ value: Double) -> Text
```

## 参数

- **value**：音调升高或降低的幅度。介于 `-1` 和 `0` 之间的值会降低音调，而介于 `0` 和 `1` 之间的值会提高音调。该方法将值限制在 `-1` 到 `1` 的范围内。

## 讨论

当您想要更改朗读文本的音调时，请使用此修饰符。该值指示音调升高或降低的幅度。

## 配置旁白

- **speechAlwaysIncludesPunctuation(_:)**：设置旁白是否始终朗读文本视图中的所有标点符号。

- **speechAnnouncementsQueued(_:)**：控制是否将待处理的语音提示排队到现有语音之后，而不是打断正在进行的语音。

- **speechSpellsOutCharacters(_:)**：设置旁白是否逐字符朗读文本视图的内容。


---
source: https://developer.apple.com/documentation/SwiftUI/Text/speechAdjustedPitch(_:)
crawled: 2025-12-01T02:39:28Z
---

# speechAdjustedPitch(_:)

**Instance Method**

Raises or lowers the pitch of spoken text.

## Declaration

```swift
func speechAdjustedPitch(_ value: Double) -> Text
```

## Parameters

- **value**: The amount to raise or lower the pitch. Values between `-1` and `0` result in a lower pitch while values between `0` and `1` result in a higher pitch. The method clamps values to the range `-1` to `1`.

## Discussion

Use this modifier when you want to change the pitch of spoken text. The value indicates how much higher or lower to change the pitch.

## Configuring voiceover

- **speechAlwaysIncludesPunctuation(_:)**: Sets whether VoiceOver should always speak all punctuation in the text view.
- **speechAnnouncementsQueued(_:)**: Controls whether to queue pending announcements behind existing speech rather than interrupting speech in progress.
- **speechSpellsOutCharacters(_:)**: Sets whether VoiceOver should speak the contents of the text view character by character.

