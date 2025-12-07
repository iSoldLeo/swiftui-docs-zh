--- 来源：https://developer.apple.com/documentation/SwiftUI/View/accessibilityInputLabels(_:isEnabled:)

抓取时间：2025-11-30T21:29:13Z

---

# accessibilityInputLabels(_:isEnabled:)

**实例方法**

设置用户用于识别视图的备用输入标签。

## 声明

```swift
nonisolated func accessibilityInputLabels(_ inputLabelKeys: [LocalizedStringKey], isEnabled: Bool) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## 参数

- **inputLabelKeys**：要应用的辅助功能输入标签。

- **isEnabled**：如果为 true，则应用辅助功能输入标签；否则，辅助功能输入标签保持不变。

## 说明

按重要性降序提供标签。语音控制和完整键盘访问会使用这些输入标签。

## 应用标签

- **accessibilityLabel(_:)**：为视图添加描述其内容的标签。

- **accessibilityLabel(_:isEnabled:)**：为视图添加描述其内容的标签。

- **accessibilityLabel(content:)**：为视图添加描述其内容的标签。

- **accessibilityInputLabels(_:)**：设置用户用于识别视图的备用输入标签。

- **accessibilityLabeledPair(role:id:in:)**：将表示标签的辅助功能元素与匹配内容的元素配对。

- **AccessibilityLabeledPairRole**：辅助功能元素在标签/内容对中的作用。


---
source: https://developer.apple.com/documentation/SwiftUI/View/accessibilityInputLabels(_:isEnabled:)
crawled: 2025-11-30T21:29:13Z
---

# accessibilityInputLabels(_:isEnabled:)

**Instance Method**

Sets alternate input labels with which users identify a view.

## Declaration

```swift
nonisolated func accessibilityInputLabels(_ inputLabelKeys: [LocalizedStringKey], isEnabled: Bool) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## Parameters

- **inputLabelKeys**: The accessibility input labels to apply.
- **isEnabled**: If true the accessibility input labels are applied; otherwise the accessibility input labels are unchanged.

## Discussion

Provide labels in descending order of importance. Voice Control and Full Keyboard Access use the input labels.



## Applying labels

- **accessibilityLabel(_:)**: Adds a label to the view that describes its contents.
- **accessibilityLabel(_:isEnabled:)**: Adds a label to the view that describes its contents.
- **accessibilityLabel(content:)**: Adds a label to the view that describes its contents.
- **accessibilityInputLabels(_:)**: Sets alternate input labels with which users identify a view.
- **accessibilityLabeledPair(role:id:in:)**: Pairs an accessibility element representing a label with the element for the matching content.
- **AccessibilityLabeledPairRole**: The role of an accessibility element in a label / content pair.

