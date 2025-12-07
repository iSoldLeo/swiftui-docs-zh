--- 来源：https://developer.apple.com/documentation/SwiftUI/View/accessibilityInputLabels(_:)

抓取时间：2025-12-02T17:44:12Z

---

# accessibilityInputLabels(_:)

**实例方法**

设置用户用于识别视图的备用输入标签。

## 声明

```swift
nonisolated func accessibilityInputLabels(_ inputLabelKeys: [LocalizedStringKey]) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## 说明

按重要性降序提供标签。语音控制和完整键盘访问功能会使用这些输入标签。

## 应用标签

- **accessibilityLabel(_:)**：向视图添加描述其内容的标签。

- **accessibilityLabel(_:isEnabled:)**：向视图添加描述其内容的标签。

- **accessibilityLabel(content:)**：向视图添加描述其内容的标签。

- **accessibilityInputLabels(_:isEnabled:)**：设置用户用于识别视图的备用输入标签。

- **accessibilityLabeledPair(role:id:in:)**：将表示标签的辅助功能元素与对应内容的元素配对。

- **AccessibilityLabeledPairRole**：辅助功能元素在标签/内容对中的作用。


---
source: https://developer.apple.com/documentation/SwiftUI/View/accessibilityInputLabels(_:)
crawled: 2025-12-02T17:44:12Z
---

# accessibilityInputLabels(_:)

**Instance Method**

Sets alternate input labels with which users identify a view.

## Declaration

```swift
nonisolated func accessibilityInputLabels(_ inputLabelKeys: [LocalizedStringKey]) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## Discussion

Provide labels in descending order of importance. Voice Control and Full Keyboard Access use the input labels.



## Applying labels

- **accessibilityLabel(_:)**: Adds a label to the view that describes its contents.
- **accessibilityLabel(_:isEnabled:)**: Adds a label to the view that describes its contents.
- **accessibilityLabel(content:)**: Adds a label to the view that describes its contents.
- **accessibilityInputLabels(_:isEnabled:)**: Sets alternate input labels with which users identify a view.
- **accessibilityLabeledPair(role:id:in:)**: Pairs an accessibility element representing a label with the element for the matching content.
- **AccessibilityLabeledPairRole**: The role of an accessibility element in a label / content pair.

