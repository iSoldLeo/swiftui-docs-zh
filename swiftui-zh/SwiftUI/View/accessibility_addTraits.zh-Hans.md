--- 来源：https://developer.apple.com/documentation/SwiftUI/View/accessibility(addTraits:)

抓取时间：2025-12-03T05:35:25Z

---

# accessibility(addTraits:)

**实例方法**

向视图添加指定的特性。

## 声明

```swift
nonisolated func accessibility(addTraits traits: AccessibilityTraits) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## 辅助功能修饰符

- **accessibility(label:)**：向视图添加一个标签，用于描述其内容。

- **accessibility(value:)**：添加视图所包含值的文本描述。

- **accessibility(hidden:)**：指定是否从系统辅助功能中隐藏此视图。

- **accessibility(identifier:)**：使用指定的字符串来标识视图。

- **accessibility(selectionIdentifier:)**：设置此视图辅助功能元素的选择标识符。

- **accessibility(hint:)**：告知用户执行视图操作后将发生什么。

- **accessibility(activationPoint:)**：指定视图中激活操作发生的位置。

- **accessibility(inputLabels:)**：设置用户用于识别视图的备用输入标签。

- **accessibility(removeTraits:)**：从此视图中移除指定的属性。

- **accessibility(sortPriority:)**：设置此视图辅助功能元素相对于同一级别其他元素的排序优先级。


---
source: https://developer.apple.com/documentation/SwiftUI/View/accessibility(addTraits:)
crawled: 2025-12-03T05:35:25Z
---

# accessibility(addTraits:)

**Instance Method**

Adds the given traits to the view.

## Declaration

```swift
nonisolated func accessibility(addTraits traits: AccessibilityTraits) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## Accessibility modifiers

- **accessibility(label:)**: Adds a label to the view that describes its contents.
- **accessibility(value:)**: Adds a textual description of the value that the view contains.
- **accessibility(hidden:)**: Specifies whether to hide this view from system accessibility features.
- **accessibility(identifier:)**: Uses the specified string to identify the view.
- **accessibility(selectionIdentifier:)**: Sets a selection identifier for this view’s accessibility element.
- **accessibility(hint:)**: Communicates to the user what happens after performing the view’s action.
- **accessibility(activationPoint:)**: Specifies the point where activations occur in the view.
- **accessibility(inputLabels:)**: Sets alternate input labels with which users identify a view.
- **accessibility(removeTraits:)**: Removes the given traits from this view.
- **accessibility(sortPriority:)**: Sets the sort priority order for this view’s accessibility element, relative to other elements at the same level.

