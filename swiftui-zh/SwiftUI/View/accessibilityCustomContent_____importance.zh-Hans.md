--- 来源：https://developer.apple.com/documentation/SwiftUI/View/accessibilityCustomContent(_:_:importance:)

抓取时间：2025-11-30T21:29:21Z

---

# accessibilityCustomContent(_:_:importance:)

**实例方法**

向视图添加额外的辅助功能信息。

## 声明

```swift
nonisolated func accessibilityCustomContent(_ key: AccessibilityCustomContentKey, _ value: Text?, importance: AXCustomContent.Importance = .default) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## 参数

- **key**：用于指定额外辅助功能信息条目的标识符和标签的键。

- **value**：额外辅助功能信息的文本值。例如：“landscape”。值为 `nil` 将删除之前添加的、具有相同标识符的任何 `key` 的额外信息条目。

## 讨论

使用此方法可以添加您希望辅助功能用户能够访问的关于此元素的信息，这些信息超越了标签、值和提示等基本信息。例如，`accessibilityCustomContent` 可用于添加有关照片方向或照片中人数的信息。

## 添加自定义描述

- **AccessibilityCustomContentKey**：用于指定与附加辅助功能信息条目关联的标识符和标签的键。


---
source: https://developer.apple.com/documentation/SwiftUI/View/accessibilityCustomContent(_:_:importance:)
crawled: 2025-11-30T21:29:21Z
---

# accessibilityCustomContent(_:_:importance:)

**Instance Method**

Add additional accessibility information to the view.

## Declaration

```swift
nonisolated func accessibilityCustomContent(_ key: AccessibilityCustomContentKey, _ value: Text?, importance: AXCustomContent.Importance = .default) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## Parameters

- **key**: Key used to specify the identifier and label of the of the additional accessibility information entry.
- **value**: Text value for the additional accessibility information. For example: “landscape.” A value of `nil` will remove any entry of additional information added earlier for any `key` with the same identifier.

## Discussion

Use this method to add information you want accessibility users to be able to access about this element, beyond the basics of label, value, and hint. For example, `accessibilityCustomContent` can be used to add information about the orientation of a photograph, or the number of people found in the picture.



## Adding custom descriptions

- **AccessibilityCustomContentKey**: Key used to specify the identifier and label associated with an entry of additional accessibility information.

