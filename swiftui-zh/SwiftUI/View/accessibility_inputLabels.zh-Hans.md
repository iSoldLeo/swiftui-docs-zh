--- 来源：https://developer.apple.com/documentation/SwiftUI/View/accessibility(inputLabels:)

抓取时间：2025-12-01T10:24:31Z

---

# accessibility(inputLabels:)

**实例方法**

设置用户用于识别视图的备用输入标签。

## 声明

```swift
nonisolated func accessibility(inputLabels: [Text]) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## 参数

- **inputLabels**：一个包含 [Text](../Text.zh-Hans.md) 个元素的数组，用作输入标签。

## 说明

按重要性降序提供标签。语音控制和完整键盘访问功能会使用输入标签。

## 辅助功能修饰符

- **accessibility(label:)**：向视图添加一个描述其内容的标签。

- **accessibility(value:)**：添加视图所包含值的文本描述。

- **accessibility(hidden:)**：指定是否从系统辅助功能中隐藏此视图。

- **accessibility(identifier:)**：使用指定的字符串标识视图。

- **accessibility(selectionIdentifier:)**：为此视图的辅助功能元素设置选择标识符。

- **accessibility(hint:)**：告知用户执行视图操作后会发生什么。

- **accessibility(activationPoint:)**：指定视图中激活操作发生的点。

- **accessibility(addTraits:)**：向视图添加指定的特性。

- **accessibility(removeTraits:)**：从视图中移除指定的特性。

- **accessibility(sortPriority:)**：设置此视图辅助功能元素相对于同一级别其他元素的排序优先级。


---
source: https://developer.apple.com/documentation/SwiftUI/View/accessibility(inputLabels:)
crawled: 2025-12-01T10:24:31Z
---

# accessibility(inputLabels:)

**Instance Method**

Sets alternate input labels with which users identify a view.

## Declaration

```swift
nonisolated func accessibility(inputLabels: [Text]) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## Parameters

- **inputLabels**: An array of [Text](../Text.zh-Hans.md) elements to use as input labels.

## Discussion

Provide labels in descending order of importance. Voice Control and Full Keyboard Access use the input labels.



## Accessibility modifiers

- **accessibility(label:)**: Adds a label to the view that describes its contents.
- **accessibility(value:)**: Adds a textual description of the value that the view contains.
- **accessibility(hidden:)**: Specifies whether to hide this view from system accessibility features.
- **accessibility(identifier:)**: Uses the specified string to identify the view.
- **accessibility(selectionIdentifier:)**: Sets a selection identifier for this view’s accessibility element.
- **accessibility(hint:)**: Communicates to the user what happens after performing the view’s action.
- **accessibility(activationPoint:)**: Specifies the point where activations occur in the view.
- **accessibility(addTraits:)**: Adds the given traits to the view.
- **accessibility(removeTraits:)**: Removes the given traits from this view.
- **accessibility(sortPriority:)**: Sets the sort priority order for this view’s accessibility element, relative to other elements at the same level.

