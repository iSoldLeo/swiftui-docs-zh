--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/speechSpellsOutCharacters(_:)

抓取时间：2025-12-02T21:48:39Z

---

# speechSpellsOutCharacters(_:)

**实例方法**

设置 VoiceOver 是否应该逐个字符地朗读文本视图的内容。

## 声明

```swift
func speechSpellsOutCharacters(_ value: Bool = true) -> Text
```

## 参数

- **value**：一个布尔值，当 `true` 为真时，表示 VoiceOver 应该逐个字符地朗读文本。默认值为 `true`。

## 说明

如果您希望 VoiceOver 逐个字符地朗读文本，请使用此修饰符。这对于不适合连读的文本非常重要，例如：

- 并非单词的缩写，例如 APPL，读作“A-P-P-L”。

- 代表一系列数字的数字，例如 25，读作“two-five”而不是“twenty-five”。

## 配置旁白

- **speechAdjustedPitch(_:)**：提高或降低朗读文本的音调。

- **speechAlwaysIncludesPunctuation(_:)**：设置旁白是否始终朗读文本视图中的所有标点符号。

- **speechAnnouncementsQueued(_:)**：控制是否将待处理的语音提示排队到现有语音之后，而不是打断正在进行的语音。


---
source: https://developer.apple.com/documentation/SwiftUI/Text/speechSpellsOutCharacters(_:)
crawled: 2025-12-02T21:48:39Z
---

# speechSpellsOutCharacters(_:)

**Instance Method**

Sets whether VoiceOver should speak the contents of the text view character by character.

## Declaration

```swift
func speechSpellsOutCharacters(_ value: Bool = true) -> Text
```

## Parameters

- **value**: A Boolean value that when `true` indicates VoiceOver should speak text as individual characters. Defaults to `true`.

## Discussion

Use this modifier when you want VoiceOver to speak text as individual letters, character by character. This is important for text that is not meant to be spoken together, like:

- An acronym that isn’t a word, like APPL, spoken as “A-P-P-L”.
- A number representing a series of digits, like 25, spoken as “two-five” rather than “twenty-five”.

## Configuring voiceover

- **speechAdjustedPitch(_:)**: Raises or lowers the pitch of spoken text.
- **speechAlwaysIncludesPunctuation(_:)**: Sets whether VoiceOver should always speak all punctuation in the text view.
- **speechAnnouncementsQueued(_:)**: Controls whether to queue pending announcements behind existing speech rather than interrupting speech in progress.

