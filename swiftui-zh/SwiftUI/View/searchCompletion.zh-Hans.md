--- 来源：https://developer.apple.com/documentation/SwiftUI/View/searchCompletion(_:)

抓取时间：2025-12-02T17:31:38Z

---

# searchCompletion(_:)

**实例方法**

当此视图用作搜索建议时，将一个完整的字符串与该视图的值关联起来。

## 声明

```swift
nonisolated func searchCompletion(_ completion: String) -> some View

```

## 说明

使用此方法可将一个完整的字符串与搜索建议列表上下文中的视图关联起来。当选择该视图时，系统会使用此值来替换当前正在编辑的关联搜索字段的部分文本。

在 tvOS 上，您提供给此修饰符的字符串将用于显示关联的建议以及替换搜索字段的部分文本。

```swift
SearchPlaceholderView()
    .searchable(text: $text) {
        Text("🍎").searchCompletion("apple")
        Text("🍐").searchCompletion("pear")
        Text("🍌").searchCompletion("banana")
    }
```

## 提供搜索建议

- **建议搜索词**：为在应用中搜索内容的用户提供建议。

- **searchSuggestions(_:)**：配置此视图的搜索建议。

- **searchSuggestions(_:for:)**：配置在此视图中显示搜索建议的方式。

- **searchable(text:tokens:suggestedTokens:placement:prompt:token:)**：将此视图标记为可搜索，支持文本、词元和建议。

- **SearchSuggestionsPlacement**：SwiftUI 显示搜索建议的方式。


---
source: https://developer.apple.com/documentation/SwiftUI/View/searchCompletion(_:)
crawled: 2025-12-02T17:31:38Z
---

# searchCompletion(_:)

**Instance Method**

Associates a fully formed string with the value of this view when used as a search suggestion.

## Declaration

```swift
nonisolated func searchCompletion(_ completion: String) -> some View

```

## Discussion

Use this method to associate a fully formed string with a view that is within a search suggestion list context. The system uses this value when the view is selected to replace the partial text being currently edited of the associated search field.

On tvOS, the string that you provide to the this modifier is used when displaying the associated suggestion and when replacing the partial text of the search field.

```swift
SearchPlaceholderView()
    .searchable(text: $text) {
        Text("🍎").searchCompletion("apple")
        Text("🍐").searchCompletion("pear")
        Text("🍌").searchCompletion("banana")
    }
```

## Making search suggestions

- **Suggesting search terms**: Provide suggestions to people searching for content in your app.
- **searchSuggestions(_:)**: Configures the search suggestions for this view.
- **searchSuggestions(_:for:)**: Configures how to display search suggestions within this view.
- **searchable(text:tokens:suggestedTokens:placement:prompt:token:)**: Marks this view as searchable with text, tokens, and suggestions.
- **SearchSuggestionsPlacement**: The ways that SwiftUI displays search suggestions.

