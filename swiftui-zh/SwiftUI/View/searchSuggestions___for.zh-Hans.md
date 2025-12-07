--- 来源：https://developer.apple.com/documentation/SwiftUI/View/searchSuggestions(_:for:)

抓取时间：2025-11-30T21:16:43Z

---

# searchSuggestions(_:for:)

**实例方法**

配置此视图中搜索建议的显示方式。

## 声明

```swift
nonisolated func searchSuggestions(_ visibility: Visibility, for placements: SearchSuggestionsPlacement.Set) -> some View

```

## 参数

- **visibility**：指定位置的搜索建议可见性。

- **placements**：要设置搜索建议可见性的位置集合。

## 说明

SwiftUI 会根据平台、搜索框位置和尺寸类等多种因素以不同的方式呈现搜索建议。如果您希望仅在特定条件下以特定方式显示建议，请使用此修饰符。例如，您可以选择尽可能在菜单中显示搜索建议，否则直接筛选数据源。

```swift
enum FruitSuggestion: String, Identifiable {
    case apple, banana, orange
    var id: Self { self }
}

@State private var text = ""
@State private var suggestions: [FruitSuggestion] = []

var body: some View {
    MainContent()
        .searchable(text: $text) {
            ForEach(suggestions) { suggestion
                Text(suggestion.rawValue)
                    .searchCompletion(suggestion.rawValue)
            }
            .searchSuggestions(.hidden, for: .content)
        }
}
```

## 生成搜索建议

- **建议搜索词**：为在您的应用中搜索内容的用户提供搜索建议。

- **searchSuggestions(_:)**：配置此视图的搜索建议。

- **searchCompletion(_:)**：将一个完整的字符串与此视图的值关联起来，以便用作搜索建议。

- **searchable(text:tokens:suggestedTokens:placement:prompt:token:)**：将此视图标记为可搜索，支持文本、词元和搜索建议。

- **SearchSuggestionsPlacement**：SwiftUI 显示搜索建议的方式。


---
source: https://developer.apple.com/documentation/SwiftUI/View/searchSuggestions(_:for:)
crawled: 2025-11-30T21:16:43Z
---

# searchSuggestions(_:for:)

**Instance Method**

Configures how to display search suggestions within this view.

## Declaration

```swift
nonisolated func searchSuggestions(_ visibility: Visibility, for placements: SearchSuggestionsPlacement.Set) -> some View

```

## Parameters

- **visibility**: The visibility of the search suggestions for the specified locations.
- **placements**: The set of locations in which to set the visibility of search suggestions.

## Discussion

SwiftUI presents search suggestions differently depending on several factors, like the platform, the position of the search field, and the size class. Use this modifier when you want to only display suggestions in certain ways under certain conditions. For example, you might choose to display suggestions in a menu when possible, but directly filter your data source otherwise.

```swift
enum FruitSuggestion: String, Identifiable {
    case apple, banana, orange
    var id: Self { self }
}

@State private var text = ""
@State private var suggestions: [FruitSuggestion] = []

var body: some View {
    MainContent()
        .searchable(text: $text) {
            ForEach(suggestions) { suggestion
                Text(suggestion.rawValue)
                    .searchCompletion(suggestion.rawValue)
            }
            .searchSuggestions(.hidden, for: .content)
        }
}
```

## Making search suggestions

- **Suggesting search terms**: Provide suggestions to people searching for content in your app.
- **searchSuggestions(_:)**: Configures the search suggestions for this view.
- **searchCompletion(_:)**: Associates a fully formed string with the value of this view when used as a search suggestion.
- **searchable(text:tokens:suggestedTokens:placement:prompt:token:)**: Marks this view as searchable with text, tokens, and suggestions.
- **SearchSuggestionsPlacement**: The ways that SwiftUI displays search suggestions.

