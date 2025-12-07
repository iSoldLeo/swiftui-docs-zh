--- 来源：https://developer.apple.com/documentation/SwiftUI/View/accessibility(label:)

抓取时间：2025-12-03T05:35:19Z

---

# accessibility(label:)

**实例方法**

为视图添加一个描述其内容的标签。

## 声明

```swift
nonisolated func accessibility(label: Text) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## 讨论

使用此方法为不显示文本的视图（例如图标）提供辅助功能标签。例如，您可以使用此方法为播放音乐的按钮添加“播放”标签。请勿在标签中包含用户已了解的信息。例如，请勿使用“播放按钮”标签，因为按钮已经具有标识其为按钮的特征。

## 辅助功能修饰符

- **accessibility(value:)**：为视图包含的值添加文本描述。

- **accessibility(hidden:)**：指定是否从系统辅助功能中隐藏此视图。

- **accessibility(identifier:)**：使用指定的字符串标识视图。

- **accessibility(selectionIdentifier:)**：为此视图的辅助功能元素设置选择标识符。

- **accessibility(hint:)**：告知用户执行视图操作后会发生什么。

- **accessibility(activationPoint:)**：指定视图中激活操作发生的点。

- **accessibility(inputLabels:)**：设置用户用于标识视图的备用输入标签。

- **accessibility(addTraits:)**：向视图添加指定的特性。

- **accessibility(removeTraits:)**：从视图中移除指定的特性。

- **accessibility(sortPriority:)**：设置此视图辅助功能元素相对于同一级别其他元素的排序优先级。


---
source: https://developer.apple.com/documentation/SwiftUI/View/accessibility(label:)
crawled: 2025-12-03T05:35:19Z
---

# accessibility(label:)

**Instance Method**

Adds a label to the view that describes its contents.

## Declaration

```swift
nonisolated func accessibility(label: Text) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## Discussion

Use this method to provide an accessibility label for a view that doesn’t display text, like an icon. For example, you could use this method to label a button that plays music with the text “Play”. Don’t include text in the label that repeats information that users already have. For example, don’t use the label “Play button” because a button already has a trait that identifies it as a button.

## Accessibility modifiers

- **accessibility(value:)**: Adds a textual description of the value that the view contains.
- **accessibility(hidden:)**: Specifies whether to hide this view from system accessibility features.
- **accessibility(identifier:)**: Uses the specified string to identify the view.
- **accessibility(selectionIdentifier:)**: Sets a selection identifier for this view’s accessibility element.
- **accessibility(hint:)**: Communicates to the user what happens after performing the view’s action.
- **accessibility(activationPoint:)**: Specifies the point where activations occur in the view.
- **accessibility(inputLabels:)**: Sets alternate input labels with which users identify a view.
- **accessibility(addTraits:)**: Adds the given traits to the view.
- **accessibility(removeTraits:)**: Removes the given traits from this view.
- **accessibility(sortPriority:)**: Sets the sort priority order for this view’s accessibility element, relative to other elements at the same level.

