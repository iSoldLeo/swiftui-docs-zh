---
来源： https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityLabel(_:isEnabled:)
抓取时间： 2025-11-30T21:31:58Z
---

# accessibilityLabel(_:isEnabled:)

**实例方法**

为视图添加一个描述其内容的标签。

## 声明

```swift
nonisolated func accessibilityLabel(_ label: LocalizedStringResource, isEnabled: Bool) -> ModifiedContent<Content, Modifier>
```

## 参数

- **label**：要应用的辅助功能标签。
- **isEnabled**：如果为 true，则应用辅助功能标签；否则辅助功能标签保持不变。

## 讨论

使用此方法可为不显示文本的视图（如图标）提供辅助功能标签。例如，您可以使用此方法为播放音乐的按钮标注 "播放 "文字。不要在标签中包含重复用户已有信息的文本。例如，不要使用 "播放按钮 "标签，因为按钮已经有了识别其为按钮的特征。


---
source: https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityLabel(_:isEnabled:)
crawled: 2025-11-30T21:31:58Z
---

# accessibilityLabel(_:isEnabled:)

**Instance Method**

Adds a label to the view that describes its contents.

## Declaration

```swift
nonisolated func accessibilityLabel(_ label: LocalizedStringResource, isEnabled: Bool) -> ModifiedContent<Content, Modifier>
```

## Parameters

- **label**: The accessibility label to apply.
- **isEnabled**: If true the accessibility label is applied; otherwise the accessibility label is unchanged.

## Discussion

Use this method to provide an accessibility label for a view that doesn’t display text, like an icon. For example, you could use this method to label a button that plays music with the text “Play”. Don’t include text in the label that repeats information that users already have. For example, don’t use the label “Play button” because a button already has a trait that identifies it as a button.

