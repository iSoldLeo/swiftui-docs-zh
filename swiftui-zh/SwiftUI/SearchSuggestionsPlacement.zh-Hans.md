---
来源： https://developer.apple.com/documentation/SwiftUI/SearchSuggestionsPlacement
抓取时间： 2025-12-02T17:31:40Z
---

# SearchSuggestionsPlacement

**Structure**

SwiftUI 显示搜索建议的方式。

## 声明

```swift
struct SearchSuggestionsPlacement
```

## 概览

您可以使用 [searchSuggestions(_:for:)](View/searchSuggestions___for.zh-Hans.md) 修饰符来影响 SwiftUI 显示哪些模式的搜索建议：

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
            ForEach(suggestions) { suggestion in
                Text(suggestion.rawValue)
                    .searchCompletion(suggestion.rawValue)
            }
            .searchSuggestions(.hidden, for: .content)
        }
}
```修改器

在上例中，SwiftUI 只在建议菜单中显示搜索建议。如果您想在一个容器中显示搜索建议，例如与您自己的搜索结果集内联，您可能需要这样做。

您可以通过查询搜索建议中的[searchSuggestionsPlacement](EnvironmentValues/searchSuggestionsPlacement.zh-Hans.md)环境值来获取当前搜索建议的位置。

## 获取位置

- **automatic**：搜索建议会根据周围环境自动呈现。
- **content**：搜索建议会显示在应用程序的主要内容中。
- **menu**：搜索建议显示在搜索字段的菜单中。

## 支持类型

- **SearchSuggestionsPlacement.Set**：一套高效的搜索建议显示模式。

## 制作搜索建议

- **搜索建议**：向在你的应用程序中搜索内容的人提供建议。
- **searchSuggestions(_:)**：配置此视图的搜索建议。
- **searchSuggestions(_:for:)**：配置如何在此视图中显示搜索建议。
- **searchCompletion(_:)**：当用作搜索建议时，将一个完整的字符串与此视图的值关联。
- **searchable(text:tokens:suggestedTokens:placement:prompt:token:)**：将此视图标记为可使用文本、标记和建议进行搜索。

## 符合

- 可等同
- 可发送
- 可发送元数据类型


---
source: https://developer.apple.com/documentation/SwiftUI/SearchSuggestionsPlacement
crawled: 2025-12-02T17:31:40Z
---

# SearchSuggestionsPlacement

**Structure**

The ways that SwiftUI displays search suggestions.

## Declaration

```swift
struct SearchSuggestionsPlacement
```

## Overview

You can influence which modes SwiftUI displays search suggestions for by using the [searchSuggestions(_:for:)](View/searchSuggestions___for.zh-Hans.md) modifier:

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
            ForEach(suggestions) { suggestion in
                Text(suggestion.rawValue)
                    .searchCompletion(suggestion.rawValue)
            }
            .searchSuggestions(.hidden, for: .content)
        }
}
```

In the above example, SwiftUI only displays search suggestions in a suggestions menu. You might want to do this when you want to render search suggestions in a container, like inline with your own set of search results.

You can get the current search suggestion placement by querying the [searchSuggestionsPlacement](EnvironmentValues/searchSuggestionsPlacement.zh-Hans.md) environment value in your search suggestions.

## Getting placements

- **automatic**: Search suggestions render automatically based on the surrounding context.
- **content**: Search suggestions render in the main content of the app.
- **menu**: Search suggestions render inside of a menu attached to the search field.

## Supporting types

- **SearchSuggestionsPlacement.Set**: An efficient set of search suggestion display modes.

## Making search suggestions

- **Suggesting search terms**: Provide suggestions to people searching for content in your app.
- **searchSuggestions(_:)**: Configures the search suggestions for this view.
- **searchSuggestions(_:for:)**: Configures how to display search suggestions within this view.
- **searchCompletion(_:)**: Associates a fully formed string with the value of this view when used as a search suggestion.
- **searchable(text:tokens:suggestedTokens:placement:prompt:token:)**: Marks this view as searchable with text, tokens, and suggestions.

## Conforms To

- Equatable
- Sendable
- SendableMetatype

