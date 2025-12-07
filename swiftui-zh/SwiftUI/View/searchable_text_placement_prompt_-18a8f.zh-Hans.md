--- 来源：https://developer.apple.com/documentation/SwiftUI/View/searchable(text:placement:prompt:)-18a8f

抓取时间：2025-11-30T20:49:57Z

---

# searchable(text:placement:prompt:)

**实例方法**

将此视图标记为可搜索，从而配置搜索字段的显示。

## 声明

```swift
nonisolated func searchable(text: Binding<String>, placement: SearchFieldPlacement = .automatic, prompt: Text? = nil) -> some View

```

## 参数

- **text**：要在搜索字段中显示和编辑的文本。

- **placement**：搜索字段在包含视图层次结构中的首选位置。

- **prompt**：一个 [Text](../Text.zh-Hans.md) 视图，用于显示搜索字段的提示信息，为用户提供搜索内容的指导。

## 讨论

有关使用可搜索修饰符的更多信息，请参阅 [Adding-a-search-interface-to-your-app](../Adding-a-search-interface-to-your-app.zh-Hans.md)。


---
source: https://developer.apple.com/documentation/SwiftUI/View/searchable(text:placement:prompt:)-18a8f
crawled: 2025-11-30T20:49:57Z
---

# searchable(text:placement:prompt:)

**Instance Method**

Marks this view as searchable, which configures the display of a search field.

## Declaration

```swift
nonisolated func searchable(text: Binding<String>, placement: SearchFieldPlacement = .automatic, prompt: Text? = nil) -> some View

```

## Parameters

- **text**: The text to display and edit in the search field.
- **placement**: The preferred placement of the search field within the containing view hierarchy.
- **prompt**: A [Text](../Text.zh-Hans.md) view representing the prompt of the search field which provides users with guidance on what to search for.

## Discussion

For more information about using searchable modifiers, see [Adding-a-search-interface-to-your-app](../Adding-a-search-interface-to-your-app.zh-Hans.md).

