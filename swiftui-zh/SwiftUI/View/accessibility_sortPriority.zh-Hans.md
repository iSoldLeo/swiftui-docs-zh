--- 来源：https://developer.apple.com/documentation/SwiftUI/View/accessibility(sortPriority:)

抓取时间：2025-12-03T05:35:27Z

---

# accessibility(sortPriority:)

**实例方法**

设置此视图的辅助功能元素相对于同一级别其他元素的排序优先级。

## 声明

```swift
nonisolated func accessibility(sortPriority: Double) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## 说明

数值越大，排序越靠前。默认排序优先级为零。

## 辅助功能修饰符

- **accessibility(label:)**：为视图添加描述其内容的标签。

- **accessibility(value:)**：为视图包含的值添加文本描述。

- **accessibility(hidden:)**：指定是否从系统辅助功能中隐藏此视图。

- **accessibility(identifier:)**：使用指定的字符串标识视图。

- **accessibility(selectionIdentifier:)**：为该视图的辅助功能元素设置选择标识符。

- **accessibility(hint:)**：告知用户执行视图操作后会发生什么。

- **accessibility(activationPoint:)**：指定视图中激活发生的位置。

- **accessibility(inputLabels:)**：设置用户用于标识视图的备用输入标签。

- **accessibility(addTraits:)**：向视图添加给定的特征。

- **accessibility(removeTraits:)**：从该视图中移除给定的特征。


---
source: https://developer.apple.com/documentation/SwiftUI/View/accessibility(sortPriority:)
crawled: 2025-12-03T05:35:27Z
---

# accessibility(sortPriority:)

**Instance Method**

Sets the sort priority order for this view’s accessibility element, relative to other elements at the same level.

## Declaration

```swift
nonisolated func accessibility(sortPriority: Double) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## Discussion

Higher numbers are sorted first. The default sort priority is zero.

## Accessibility modifiers

- **accessibility(label:)**: Adds a label to the view that describes its contents.
- **accessibility(value:)**: Adds a textual description of the value that the view contains.
- **accessibility(hidden:)**: Specifies whether to hide this view from system accessibility features.
- **accessibility(identifier:)**: Uses the specified string to identify the view.
- **accessibility(selectionIdentifier:)**: Sets a selection identifier for this view’s accessibility element.
- **accessibility(hint:)**: Communicates to the user what happens after performing the view’s action.
- **accessibility(activationPoint:)**: Specifies the point where activations occur in the view.
- **accessibility(inputLabels:)**: Sets alternate input labels with which users identify a view.
- **accessibility(addTraits:)**: Adds the given traits to the view.
- **accessibility(removeTraits:)**: Removes the given traits from this view.

