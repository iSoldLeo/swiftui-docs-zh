--- 来源：https://developer.apple.com/documentation/SwiftUI/View/accessibilityValue(_:isEnabled:)

抓取时间：2025-12-02T17:44:16Z

---

# accessibilityValue(_:isEnabled:)

**实例方法**

为视图包含的值添加文本描述。

## 声明

```swift
nonisolated func accessibilityValue(_ valueDescription: Text, isEnabled: Bool) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## 参数

- **valueDescription**：要应用的辅助功能值。

- **isEnabled**：如果为 true，则应用辅助功能值；否则，辅助功能值保持不变。

## 说明

仅当此值与视图的标签不同时，才可使用此方法来描述视图所表示的值。例如，对于使用 accessibilityLabel() 函数标记为“音量”的滑块，您可以使用 accessibilityValue() 函数提供当前的音量设置，例如“60%”。

## 描述值

- **accessibilityValue(_:)**：为视图中包含的值添加文本描述。


---
source: https://developer.apple.com/documentation/SwiftUI/View/accessibilityValue(_:isEnabled:)
crawled: 2025-12-02T17:44:16Z
---

# accessibilityValue(_:isEnabled:)

**Instance Method**

Adds a textual description of the value that the view contains.

## Declaration

```swift
nonisolated func accessibilityValue(_ valueDescription: Text, isEnabled: Bool) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## Parameters

- **valueDescription**: The accessibility value to apply.
- **isEnabled**: If true the accessibility value is applied; otherwise the accessibility value is unchanged.

## Discussion

Use this method to describe the value represented by a view, but only if that’s different than the view’s label. For example, for a slider that you label as “Volume” using accessibilityLabel(), you can provide the current volume setting, like “60%”, using accessibilityValue().

## Describing values

- **accessibilityValue(_:)**: Adds a textual description of the value that the view contains.

