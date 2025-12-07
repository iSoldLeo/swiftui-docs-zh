--- 来源：https://developer.apple.com/documentation/SwiftUI/View/accessibilityLabeledPair(role:id:in:)

抓取时间：2025-11-30T21:29:14Z

---

# accessibilityLabeledPair(role:id:in:)

**实例方法**

将表示标签的辅助功能元素与对应内容的元素配对。

## 声明

```swift
nonisolated func accessibilityLabeledPair<ID>(role: AccessibilityLabeledPairRole, id: ID, in namespace: Namespace.ID) -> some View where ID : Hashable

```

## 参数

- **role**：确定此元素应用作配对中的标签还是内容。

- **id**：标签/内容配对的标识符。同一命名空间内具有匹配标识符的元素将被配对。

- **namespace**：用于组织标签和内容的命名空间。同一命名空间下具有匹配标识符的标签和内容将配对在一起。

## 讨论

使用角色为 `AccessibilityLabeledPairRole.label` 的 `accessibilityLabeledPair` 来标识标签，使用角色为 `AccessibilityLabeledPairRole.content` 来标识内容。这可以改善 VoiceOver 等辅助功能在导航此类元素时的行为，使用户能够更好地理解它们之间的关系。

## 应用标签

- **accessibilityLabel(_:)**：向视图添加描述其内容的标签。

- **accessibilityLabel(_:isEnabled:)**：向视图添加描述其内容的标签。

- **accessibilityLabel(content:)**：向视图添加描述其内容的标签。

- **accessibilityInputLabels(_:)**：设置用户用于标识视图的备用输入标签。

- **accessibilityInputLabels(_:isEnabled:)**：设置用户用于识别视图的备用输入标签。

- **AccessibilityLabeledPairRole**：辅助功能元素在标签/内容对中的作用。


---
source: https://developer.apple.com/documentation/SwiftUI/View/accessibilityLabeledPair(role:id:in:)
crawled: 2025-11-30T21:29:14Z
---

# accessibilityLabeledPair(role:id:in:)

**Instance Method**

Pairs an accessibility element representing a label with the element for the matching content.

## Declaration

```swift
nonisolated func accessibilityLabeledPair<ID>(role: AccessibilityLabeledPairRole, id: ID, in namespace: Namespace.ID) -> some View where ID : Hashable

```

## Parameters

- **role**: Determines whether this element should be used as the label in the pair, or the content in the pair.
- **id**: The identifier for the label / content pair. Elements with matching identifiers within the same namespace will be paired together.
- **namespace**: The namespace used to organize label and content. Label and content under the same namespace with matching identifiers will be paired together.

## Discussion

Use `accessibilityLabeledPair` with a role of `AccessibilityLabeledPairRole.label` to identify the label, and a role of `AccessibilityLabeledPairRole.content` to identify the content. This improves the behavior of accessibility features such as VoiceOver when navigating such elements, allowing users to better understand the relationship between them.

## Applying labels

- **accessibilityLabel(_:)**: Adds a label to the view that describes its contents.
- **accessibilityLabel(_:isEnabled:)**: Adds a label to the view that describes its contents.
- **accessibilityLabel(content:)**: Adds a label to the view that describes its contents.
- **accessibilityInputLabels(_:)**: Sets alternate input labels with which users identify a view.
- **accessibilityInputLabels(_:isEnabled:)**: Sets alternate input labels with which users identify a view.
- **AccessibilityLabeledPairRole**: The role of an accessibility element in a label / content pair.

