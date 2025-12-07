--- 来源：https://developer.apple.com/documentation/SwiftUI/View/accessibilitySortPriority(_:)

抓取时间：2025-12-02T17:44:39Z

---

# accessibilitySortPriority(_:)

**实例方法**

设置此视图中辅助功能元素相对于同一级别其他元素的排序优先级。

## 声明

```swift
nonisolated func accessibilitySortPriority(_ sortPriority: Double) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## 说明

数值越大，排序越靠前。默认排序优先级为零。

## 配置转子

- **accessibilityRotorEntry(id:in:)**：定义一个显式标识符，将此视图的辅助功能元素与辅助功能转子中的一个条目关联起来。

- **accessibilityLinkedGroup(id:in:)**：链接多个辅助功能元素，使用户能够快速从一个元素导航到另一个元素，即使这些元素在辅助功能层级结构中彼此并不相邻。


---
source: https://developer.apple.com/documentation/SwiftUI/View/accessibilitySortPriority(_:)
crawled: 2025-12-02T17:44:39Z
---

# accessibilitySortPriority(_:)

**Instance Method**

Sets the sort priority order for this view’s accessibility element, relative to other elements at the same level.

## Declaration

```swift
nonisolated func accessibilitySortPriority(_ sortPriority: Double) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## Discussion

Higher numbers are sorted first. The default sort priority is zero.

## Configuring rotors

- **accessibilityRotorEntry(id:in:)**: Defines an explicit identifier tying an Accessibility element for this view to an entry in an Accessibility Rotor.
- **accessibilityLinkedGroup(id:in:)**: Links multiple accessibility elements so that the user can quickly navigate from one element to another, even when the elements are not near each other in the accessibility hierarchy.

