---
来源：https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityCustomContent(_:_:重要性:)
抓取时间：2025-11-30T21:31:46Z
---

# accessibilityCustomContent(_:_:importance:)

**实例方法**

为视图添加额外的辅助功能信息。

## 声明

```swift
nonisolated func accessibilityCustomContent(_ key: AccessibilityCustomContentKey, _ value: Text?, importance: AXCustomContent.Importance = .default) -> ModifiedContent<Content, Modifier>
```

## 参数

- **key**：用于指定附加无障碍信息条目的标识符和标签的密钥。
- **value**：附加无障碍信息的文本值。例如"景观"。如果`nil` 的值为 `nil`，则会删除先前为具有相同标识符的任何 `key` 添加的附加信息条目。

## 讨论

除了标签、值和提示等基本信息外，使用此方法还可添加希望无障碍用户能够访问的有关此元素的信息。例如，`accessibilityCustomContent` 可用来添加有关照片方向或照片中人数的信息。




---
source: https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityCustomContent(_:_:importance:)
crawled: 2025-11-30T21:31:46Z
---

# accessibilityCustomContent(_:_:importance:)

**Instance Method**

Add additional accessibility information to the view.

## Declaration

```swift
nonisolated func accessibilityCustomContent(_ key: AccessibilityCustomContentKey, _ value: Text?, importance: AXCustomContent.Importance = .default) -> ModifiedContent<Content, Modifier>
```

## Parameters

- **key**: Key used to specify the identifier and label of the of the additional accessibility information entry.
- **value**: Text value for the additional accessibility information. For example: “landscape.” A value of `nil` will remove any entry of additional information added earlier for any `key` with the same identifier.

## Discussion

Use this method to add information you want accessibility users to be able to access about this element, beyond the basics of label, value, and hint. For example, `accessibilityCustomContent` can be used to add information about the orientation of a photograph, or the number of people found in the picture.



