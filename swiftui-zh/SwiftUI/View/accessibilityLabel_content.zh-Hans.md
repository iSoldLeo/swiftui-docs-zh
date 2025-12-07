--- 来源：https://developer.apple.com/documentation/SwiftUI/View/accessibilityLabel(content:)

抓取时间：2025-12-02T17:44:11Z

---

# accessibilityLabel(content:)

**实例方法**

向视图添加一个描述其内容的标签。

## 声明

```swift
nonisolated func accessibilityLabel<V>(@ViewBuilder content: (PlaceholderContentView<Self>) -> V) -> some View where V : View

```

## 参数

- **content**：一个视图构建器闭包，接受一个表示修改后视图的代理值。您可以将修改后的视图与其他内容组合，为原始视图创建一个新的辅助功能标签。

## 说明

使用此方法可将内容附加到视图的辅助功能标签。例如，您可以使用此方法为自定义绘制的徽章或提示添加标签，而无需移除现有的辅助功能标签。

## 应用标签

- **accessibilityLabel(_:)**：为视图添加描述其内容的标签。

- **accessibilityLabel(_:isEnabled:)**：为视图添加描述其内容的标签。

- **accessibilityInputLabels(_:)**：设置用户用于识别视图的备用输入标签。

- **accessibilityInputLabels(_:isEnabled:)**：设置用户用于识别视图的备用输入标签。

- **accessibilityLabeledPair(role:id:in:)**：将表示标签的辅助功能元素与对应内容的元素配对。

- **AccessibilityLabeledPairRole**：辅助功能元素在标签/内容对中的作用。


---
source: https://developer.apple.com/documentation/SwiftUI/View/accessibilityLabel(content:)
crawled: 2025-12-02T17:44:11Z
---

# accessibilityLabel(content:)

**Instance Method**

Adds a label to the view that describes its contents.

## Declaration

```swift
nonisolated func accessibilityLabel<V>(@ViewBuilder content: (PlaceholderContentView<Self>) -> V) -> some View where V : View

```

## Parameters

- **content**: A view builder closure that takes a proxy value representing the modified view. You can combine the modified view with other content to create a new accessibility label for the original view.

## Discussion

Use this method to append content to the accessibility label for a view. For example, you could use this method to label a badge or alert that is custom drawn without removing the existing accessibility label.

## Applying labels

- **accessibilityLabel(_:)**: Adds a label to the view that describes its contents.
- **accessibilityLabel(_:isEnabled:)**: Adds a label to the view that describes its contents.
- **accessibilityInputLabels(_:)**: Sets alternate input labels with which users identify a view.
- **accessibilityInputLabels(_:isEnabled:)**: Sets alternate input labels with which users identify a view.
- **accessibilityLabeledPair(role:id:in:)**: Pairs an accessibility element representing a label with the element for the matching content.
- **AccessibilityLabeledPairRole**: The role of an accessibility element in a label / content pair.

