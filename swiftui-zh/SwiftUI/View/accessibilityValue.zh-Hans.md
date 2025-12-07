--- 来源：https://developer.apple.com/documentation/SwiftUI/View/accessibilityValue(_:)

抓取时间：2025-12-02T17:44:15Z

---

# accessibilityValue(_:)

**实例方法**

为视图包含的值添加文本描述。

## 声明

```swift
nonisolated func accessibilityValue(_ valueDescription: Text) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## 说明

仅当视图的值与标签不同时，才使用此方法描述视图所表示的值。例如，对于使用 accessibilityLabel() 标记为“音量”的滑块，您可以使用 accessibilityValue() 提供当前的音量设置，例如“60%”。

## 描述值

- **accessibilityValue(_:isEnabled:)**：为视图包含的值添加文本描述。


---
source: https://developer.apple.com/documentation/SwiftUI/View/accessibilityValue(_:)
crawled: 2025-12-02T17:44:15Z
---

# accessibilityValue(_:)

**Instance Method**

Adds a textual description of the value that the view contains.

## Declaration

```swift
nonisolated func accessibilityValue(_ valueDescription: Text) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## Discussion

Use this method to describe the value represented by a view, but only if that’s different than the view’s label. For example, for a slider that you label as “Volume” using accessibilityLabel(), you can provide the current volume setting, like “60%”, using accessibilityValue().

## Describing values

- **accessibilityValue(_:isEnabled:)**: Adds a textual description of the value that the view contains.

