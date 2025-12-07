--- 来源：https://developer.apple.com/documentation/SwiftUI/View/searchable(text:tokens:suggestedTokens:placement:prompt:token:)

抓取时间：2025-11-30T21:16:44Z

---

# searchable(text:tokens:suggestedTokens:placement:prompt:token:)

**实例方法**

将此视图标记为可搜索，支持文本、词元和搜索建议。

## 声明

```swift
nonisolated func searchable<C, T, S>(text: Binding<String>, tokens: Binding<C>, suggestedTokens: Binding<C>, placement: SearchFieldPlacement = .automatic, prompt: S, @ViewBuilder token: @escaping (C.Element) -> T) -> some View where C : MutableCollection, C : RandomAccessCollection, C : RangeReplaceableCollection, T : View, S : StringProtocol, C.Element : Identifiable

```

## 参数

- **text**：要在搜索字段中显示和编辑的文本。

- **tokens**：要在搜索字段中显示和编辑的词元集合。

- **suggestedTokens**：要显示为搜索建议的词元集合。

- **placement**：搜索字段在包含视图层次结构中的首选位置。

- **prompt**：表示搜索字段提示的字符串，用于指导用户搜索内容。

- **token**：视图构建器，可根据令牌中的元素创建视图。

## 讨论

有关使用可搜索修饰符的更多信息，请参阅 [Adding-a-search-interface-to-your-app](../Adding-a-search-interface-to-your-app.zh-Hans.md)。

## 提供搜索建议

- **建议搜索词**：为在应用中搜索内容的用户提供建议。

- **searchSuggestions(_:)**：配置此视图的搜索建议。

- **searchSuggestions(_:for:)**：配置如何在此视图中显示搜索建议。

- **searchCompletion(_:)**：将一个完整的字符串与此视图的值关联起来，用于显示搜索建议。

- **SearchSuggestionsPlacement**：SwiftUI 显示搜索建议的方式。


---
source: https://developer.apple.com/documentation/SwiftUI/View/searchable(text:tokens:suggestedTokens:placement:prompt:token:)
crawled: 2025-11-30T21:16:44Z
---

# searchable(text:tokens:suggestedTokens:placement:prompt:token:)

**Instance Method**

Marks this view as searchable with text, tokens, and suggestions.

## Declaration

```swift
nonisolated func searchable<C, T, S>(text: Binding<String>, tokens: Binding<C>, suggestedTokens: Binding<C>, placement: SearchFieldPlacement = .automatic, prompt: S, @ViewBuilder token: @escaping (C.Element) -> T) -> some View where C : MutableCollection, C : RandomAccessCollection, C : RangeReplaceableCollection, T : View, S : StringProtocol, C.Element : Identifiable

```

## Parameters

- **text**: The text to display and edit in the search field.
- **tokens**: A collection of tokens to display and edit in the search field.
- **suggestedTokens**: A collection of tokens to display as suggestions.
- **placement**: The preferred placement of the search field within the containing view hierarchy.
- **prompt**: A string representing the prompt of the search field which provides users with guidance on what to search for.
- **token**: A view builder that creates a view given an element in tokens.

## Discussion

For more information about using searchable modifiers, see [Adding-a-search-interface-to-your-app](../Adding-a-search-interface-to-your-app.zh-Hans.md).

## Making search suggestions

- **Suggesting search terms**: Provide suggestions to people searching for content in your app.
- **searchSuggestions(_:)**: Configures the search suggestions for this view.
- **searchSuggestions(_:for:)**: Configures how to display search suggestions within this view.
- **searchCompletion(_:)**: Associates a fully formed string with the value of this view when used as a search suggestion.
- **SearchSuggestionsPlacement**: The ways that SwiftUI displays search suggestions.

