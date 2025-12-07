---
来源： https://developer.apple.com/documentation/SwiftUI/AccessibilityLabeledPairRole
抓取时间： 2025-12-02T17:44:14Z
---

# 无障碍标签配对角色

**Enumeration**

无障碍元素在标签/内容对中的作用。

### 声明

```swift
@frozen enum AccessibilityLabeledPairRole
```

## 获取角色

- **AccessibilityLabeledPairRole.content**：该元素表示标签/内容对的内容部分。
- **AccessibilityLabeledPairRole.label**：该元素表示标签/内容对中的标签部分。

## 应用标签

- **accessibilityLabel(_:)**：为视图添加描述其内容的标签。
- **accessibilityLabel(_:isEnabled:)**：为视图添加描述其内容的标签。
- **accessibilityLabel(content:)**：为视图添加描述其内容的标签。
- **accessibilityInputLabels(_:)**：设置备用输入标签，以便用户识别视图。
- **accessibilityInputLabels(_:isEnabled:)**：设置用户识别视图的备用输入标签。
- **accessibilityLabeledPair(role:id:in:)**：将代表标签的可访问性元素与匹配内容的元素配对。

## 符合

- 比特可复制
- 可复制
- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/AccessibilityLabeledPairRole
crawled: 2025-12-02T17:44:14Z
---

# AccessibilityLabeledPairRole

**Enumeration**

The role of an accessibility element in a label / content pair.

## Declaration

```swift
@frozen enum AccessibilityLabeledPairRole
```

## Getting roles

- **AccessibilityLabeledPairRole.content**: This element represents the content part of the label / content pair.
- **AccessibilityLabeledPairRole.label**: This element represents the label part of the label / content pair.

## Applying labels

- **accessibilityLabel(_:)**: Adds a label to the view that describes its contents.
- **accessibilityLabel(_:isEnabled:)**: Adds a label to the view that describes its contents.
- **accessibilityLabel(content:)**: Adds a label to the view that describes its contents.
- **accessibilityInputLabels(_:)**: Sets alternate input labels with which users identify a view.
- **accessibilityInputLabels(_:isEnabled:)**: Sets alternate input labels with which users identify a view.
- **accessibilityLabeledPair(role:id:in:)**: Pairs an accessibility element representing a label with the element for the matching content.

## Conforms To

- BitwiseCopyable
- Copyable
- Equatable
- Hashable
- Sendable
- SendableMetatype

