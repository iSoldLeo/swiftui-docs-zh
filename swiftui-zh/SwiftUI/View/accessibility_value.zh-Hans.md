--- 来源：https://developer.apple.com/documentation/SwiftUI/View/accessibility(value:)

抓取时间：2025-12-01T10:24:26Z

---

# accessibility(value:)

**实例方法**

为视图包含的值添加文本描述。

## 声明

```swift
nonisolated func accessibility(value: Text) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## 说明

使用此方法描述视图表示的值，但仅当该值与视图的标签不同时才使用。例如，对于使用 [accessibility(label:)](accessibility_label.zh-Hans.md) 标记为“音量”的滑块，您可以使用 [accessibility(value:)](accessibility_value.zh-Hans.md) 提供当前的音量设置，例如“60%”。

## 辅助功能修饰符

- **accessibility(label:)**：为视图添加描述其内容的标签。

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
source: https://developer.apple.com/documentation/SwiftUI/View/accessibility(value:)
crawled: 2025-12-01T10:24:26Z
---

# accessibility(value:)

**Instance Method**

Adds a textual description of the value that the view contains.

## Declaration

```swift
nonisolated func accessibility(value: Text) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## Discussion

Use this method to describe the value represented by a view, but only if that’s different than the view’s label. For example, for a slider that you label as “Volume” using [accessibility(label:)](accessibility_label.zh-Hans.md), you can provide the current volume setting, like “60%”, using [accessibility(value:)](accessibility_value.zh-Hans.md).

## Accessibility modifiers

- **accessibility(label:)**: Adds a label to the view that describes its contents.
- **accessibility(hidden:)**: Specifies whether to hide this view from system accessibility features.
- **accessibility(identifier:)**: Uses the specified string to identify the view.
- **accessibility(selectionIdentifier:)**: Sets a selection identifier for this view’s accessibility element.
- **accessibility(hint:)**: Communicates to the user what happens after performing the view’s action.
- **accessibility(activationPoint:)**: Specifies the point where activations occur in the view.
- **accessibility(inputLabels:)**: Sets alternate input labels with which users identify a view.
- **accessibility(addTraits:)**: Adds the given traits to the view.
- **accessibility(removeTraits:)**: Removes the given traits from this view.
- **accessibility(sortPriority:)**: Sets the sort priority order for this view’s accessibility element, relative to other elements at the same level.

