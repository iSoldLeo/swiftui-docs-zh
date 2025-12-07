--- 来源：https://developer.apple.com/documentation/SwiftUI/View/accessibilityLabel(_:isEnabled:)

抓取时间：2025-11-30T21:29:11Z

---

# accessibilityLabel(_:isEnabled:)

**实例方法**

为视图添加一个描述其内容的标签。

## 声明

```swift
nonisolated func accessibilityLabel(_ label: LocalizedStringResource, isEnabled: Bool) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## 参数

- **label**：要应用的辅助功能标签。

- **isEnabled**：如果为 true，则应用辅助功能标签；否则，辅助功能标签保持不变。

## 说明

使用此方法为不显示文本的视图（例如图标）提供辅助功能标签。例如，您可以使用此方法为播放音乐的按钮添加“播放”标签。标签中不要包含用户已掌握信息的重复文本。例如，不要使用“播放按钮”标签，因为按钮本身已经具有标识其为按钮的特征。

## 应用标签

- **accessibilityLabel(_:)**：为视图添加描述其内容的标签。

- **accessibilityLabel(content:)**：为视图添加描述其内容的标签。

- **accessibilityInputLabels(_:)**：设置用户用于识别视图的备用输入标签。

- **accessibilityInputLabels(_:isEnabled:)**：设置用户用于识别视图的备用输入标签。

- **accessibilityLabeledPair(role:id:in:)**：将表示标签的辅助功能元素与对应内容的元素配对。

- **AccessibilityLabeledPairRole**：辅助功能元素在标签/内容对中的作用。


---
source: https://developer.apple.com/documentation/SwiftUI/View/accessibilityLabel(_:isEnabled:)
crawled: 2025-11-30T21:29:11Z
---

# accessibilityLabel(_:isEnabled:)

**Instance Method**

Adds a label to the view that describes its contents.

## Declaration

```swift
nonisolated func accessibilityLabel(_ label: LocalizedStringResource, isEnabled: Bool) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## Parameters

- **label**: The accessibility label to apply.
- **isEnabled**: If true the accessibility label is applied; otherwise the accessibility label is unchanged.

## Discussion

Use this method to provide an accessibility label for a view that doesn’t display text, like an icon. For example, you could use this method to label a button that plays music with the text “Play”. Don’t include text in the label that repeats information that users already have. For example, don’t use the label “Play button” because a button already has a trait that identifies it as a button.

## Applying labels

- **accessibilityLabel(_:)**: Adds a label to the view that describes its contents.
- **accessibilityLabel(content:)**: Adds a label to the view that describes its contents.
- **accessibilityInputLabels(_:)**: Sets alternate input labels with which users identify a view.
- **accessibilityInputLabels(_:isEnabled:)**: Sets alternate input labels with which users identify a view.
- **accessibilityLabeledPair(role:id:in:)**: Pairs an accessibility element representing a label with the element for the matching content.
- **AccessibilityLabeledPairRole**: The role of an accessibility element in a label / content pair.

