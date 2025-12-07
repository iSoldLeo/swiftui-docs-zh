--- 来源：https://developer.apple.com/documentation/SwiftUI/View/speechAnnouncementsQueued(_:)

抓取时间：2025-11-30T21:29:28Z

---

# speechAnnouncementsQueued(_:)

**实例方法**

控制是否将待处理的语音提示排队到现有语音之后，而不是中断正在进行的语音。

## 声明

```swift
nonisolated func speechAnnouncementsQueued(_ value: Bool = true) -> some View

```

## 参数

- **value**：一个布尔值，用于确定 VoiceOver 是立即朗读文本更改，还是将其排队到现有语音之后。默认值为 `true`。

## 说明

当您希望影响辅助功能系统朗读文本的顺序时，请使用此修饰符。当辅助功能元素的标签或值发生更改时，语音提示可以自动播放。

## 配置旁白

- **speechAdjustedPitch(_:)**：提高或降低朗读文本的音调。

- **speechAlwaysIncludesPunctuation(_:)**：设置旁白是否始终朗读文本视图中的所有标点符号。

- **speechSpellsOutCharacters(_:)**：设置旁白是否逐字符朗读文本视图中的内容。


---
source: https://developer.apple.com/documentation/SwiftUI/View/speechAnnouncementsQueued(_:)
crawled: 2025-11-30T21:29:28Z
---

# speechAnnouncementsQueued(_:)

**Instance Method**

Controls whether to queue pending announcements behind existing speech rather than interrupting speech in progress.

## Declaration

```swift
nonisolated func speechAnnouncementsQueued(_ value: Bool = true) -> some View

```

## Parameters

- **value**: A Boolean value that determines if VoiceOver speaks changes to text immediately or enqueues them behind existing speech. Defaults to `true`.

## Discussion

Use this modifier when you want affect the order in which the accessibility system delivers spoken text. Announcements can occur automatically when the label or value of an accessibility element changes.

## Configuring VoiceOver

- **speechAdjustedPitch(_:)**: Raises or lowers the pitch of spoken text.
- **speechAlwaysIncludesPunctuation(_:)**: Sets whether VoiceOver should always speak all punctuation in the text view.
- **speechSpellsOutCharacters(_:)**: Sets whether VoiceOver should speak the contents of the text view character by character.

