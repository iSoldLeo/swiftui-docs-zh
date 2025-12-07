--- 来源：https://developer.apple.com/documentation/SwiftUI/View/searchable(text:placement:prompt:suggestions:)

抓取时间：2025-12-03T05:35:57Z

---

# searchable(text:placement:prompt:suggestions:)

**实例方法**

将此视图标记为可搜索，从而配置搜索字段的显示。

## 声明

```swift
nonisolated func searchable<S>(text: Binding<String>, placement: SearchFieldPlacement = .automatic, prompt: LocalizedStringKey, @ViewBuilder suggestions: () -> S) -> some View where S : View

```

## 参数

- **text**：要在搜索字段中显示和编辑的文本。

- **placement**：搜索字段应尝试放置在包含视图层次结构中的位置。

- **prompt**：搜索字段本地化提示的键，用于指导用户搜索内容。

- **suggestions**：一个视图构建器，用于生成填充建议列表的内容。

## 讨论

有关使用可搜索修饰符的更多信息，请参阅 [Adding-a-search-interface-to-your-app](../Adding-a-search-interface-to-your-app.zh-Hans.md)。


---
source: https://developer.apple.com/documentation/SwiftUI/View/searchable(text:placement:prompt:suggestions:)
crawled: 2025-12-03T05:35:57Z
---

# searchable(text:placement:prompt:suggestions:)

**Instance Method**

Marks this view as searchable, which configures the display of a search field.

## Declaration

```swift
nonisolated func searchable<S>(text: Binding<String>, placement: SearchFieldPlacement = .automatic, prompt: LocalizedStringKey, @ViewBuilder suggestions: () -> S) -> some View where S : View

```

## Parameters

- **text**: The text to display and edit in the search field.
- **placement**: Where the search field should attempt to be placed based on the containing view hierarchy.
- **prompt**: A key for the localized prompt of the search field which provides users with guidance on what to search for.
- **suggestions**: A view builder that produces content that populates a list of suggestions.

## Discussion

For more information about using searchable modifiers, see [Adding-a-search-interface-to-your-app](../Adding-a-search-interface-to-your-app.zh-Hans.md).

