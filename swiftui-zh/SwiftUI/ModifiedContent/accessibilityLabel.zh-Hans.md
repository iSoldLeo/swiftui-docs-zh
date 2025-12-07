---
来源： https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityLabel(_:)
抓取时间： 2025-12-02T17:47:04Z
---

# 可访问性标签(_:)

**实例方法**

为视图添加一个描述其内容的标签。

## 声明

```swift
nonisolated func accessibilityLabel(_ label: LocalizedStringResource) -> ModifiedContent<Content, Modifier>
```

## 讨论

使用此方法可为不显示文本的视图（如图标）提供可访问性标签。例如，您可以使用此方法为播放音乐的按钮标注 "播放 "文字。不要在标签中包含重复用户已有信息的文本。例如，不要使用 "播放按钮 "标签，因为按钮已经有了识别其为按钮的特征。


---
source: https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityLabel(_:)
crawled: 2025-12-02T17:47:04Z
---

# accessibilityLabel(_:)

**Instance Method**

Adds a label to the view that describes its contents.

## Declaration

```swift
nonisolated func accessibilityLabel(_ label: LocalizedStringResource) -> ModifiedContent<Content, Modifier>
```

## Discussion

Use this method to provide an accessibility label for a view that doesn’t display text, like an icon. For example, you could use this method to label a button that plays music with the text “Play”. Don’t include text in the label that repeats information that users already have. For example, don’t use the label “Play button” because a button already has a trait that identifies it as a button.

