--- 来源：https://developer.apple.com/documentation/SwiftUI/View/speechAlwaysIncludesPunctuation(_:)

抓取时间：2025-11-30T21:29:27Z

---

# speechAlwaysIncludesPunctuation(_:)

**实例方法**

设置 VoiceOver 是否始终朗读文本视图中的所有标点符号。

## 声明

```swift
nonisolated func speechAlwaysIncludesPunctuation(_ value: Bool = true) -> some View

```

## 参数

- **value**：一个布尔值，设置为 `true` 表示 VoiceOver 是否朗读文本中的所有标点符号。默认值为 `true`。

## 说明

使用此修饰符可以控制系统是否朗读文本中的标点符号。您可以将此功能用于代码或其他需要使用标点符号的文本，或者用于您希望 VoiceOver 逐字朗读您提供的文本的情况。例如，给定以下文本：

```swift
Text("All the world's a stage, " +
     "And all the men and women merely players;")
     .speechAlwaysIncludesPunctuation()
```

VoiceOver 会朗读“All the world apostrophe s a stage comma and all the men and women simply players semicolon”。

默认情况下，VoiceOver 会根据上下文朗读标点符号。

## 配置 VoiceOver

- **speechAdjustedPitch(_:)**：提高或降低朗读文本的音调。

- **speechAnnouncementsQueued(_:)**：控制是否将待处理的语音提示排队到现有语音之后，而不是打断正在进行的语音。

- **speechSpellsOutCharacters(_:)**：设置 VoiceOver 是否逐字符朗读文本视图的内容。


---
source: https://developer.apple.com/documentation/SwiftUI/View/speechAlwaysIncludesPunctuation(_:)
crawled: 2025-11-30T21:29:27Z
---

# speechAlwaysIncludesPunctuation(_:)

**Instance Method**

Sets whether VoiceOver should always speak all punctuation in the text view.

## Declaration

```swift
nonisolated func speechAlwaysIncludesPunctuation(_ value: Bool = true) -> some View

```

## Parameters

- **value**: A Boolean value that you set to `true` if VoiceOver should speak all punctuation in the text. Defaults to `true`.

## Discussion

Use this modifier to control whether the system speaks punctuation characters in the text. You might use this for code or other text where the punctuation is relevant, or where you want VoiceOver to speak a verbatim transcription of the text you provide. For example, given the text:

```swift
Text("All the world's a stage, " +
     "And all the men and women merely players;")
     .speechAlwaysIncludesPunctuation()
```

VoiceOver would speak “All the world apostrophe s a stage comma and all the men and women merely players semicolon”.

By default, VoiceOver voices punctuation based on surrounding context.

## Configuring VoiceOver

- **speechAdjustedPitch(_:)**: Raises or lowers the pitch of spoken text.
- **speechAnnouncementsQueued(_:)**: Controls whether to queue pending announcements behind existing speech rather than interrupting speech in progress.
- **speechSpellsOutCharacters(_:)**: Sets whether VoiceOver should speak the contents of the text view character by character.

