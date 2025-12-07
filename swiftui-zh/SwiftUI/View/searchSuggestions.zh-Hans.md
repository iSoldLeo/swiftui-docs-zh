--- 来源：https://developer.apple.com/documentation/SwiftUI/View/searchSuggestions(_:)

抓取时间：2025-12-02T17:31:36Z

---

# searchSuggestions(_:)

**实例方法**

配置此视图的搜索建议。

## 声明

```swift
nonisolated func searchSuggestions<S>(@ViewBuilder _ suggestions: () -> S) -> some View where S : View

```

## 参数

- **suggestions**：一个视图构建器，用于生成填充建议列表的内容。

## 说明

您可以通过向此修饰符提供视图集合，在搜索操作期间建议搜索词。当用户激活搜索界面时，界面会将建议视图显示为选项列表。通过将 [searchCompletion(_:)](searchCompletion.zh-Hans.md) 修饰符添加到视图，可以将一个字符串与每个建议视图关联起来。例如，您可以通过显示表情符号来推荐水果种类，并在每种情况下提供相应的搜索字符串作为搜索补全：

```swift
ProductList()
    .searchable(text: $text)
    .searchSuggestions {
        Text("🍎").searchCompletion("apple")
        Text("🍐").searchCompletion("pear")
        Text("🍌").searchCompletion("banana")
    }
```

当用户选择某个建议时，SwiftUI 会将搜索字段中的文本替换为搜索补全字符串。如果您省略了特定建议视图的搜索补全修饰符，SwiftUI 会显示该建议，但该建议视图不会响应点击或轻触操作。

您可以根据条件的变化更新提供的建议。

例如，您可以指定一个存储在模型中的建议数组：

```swift
ProductList()
    .searchable(text: $text)
    .searchSuggestions {
        ForEach(model.suggestedSearches) { suggestion in
            Label(suggestion.title, image: suggestion.image)
                .searchCompletion(suggestion.text)
        }
    }
```

如果模型的 `suggestedSearches` 初始为空数组，则界面最初不会显示任何建议。您可以提供逻辑，根据某些条件更新数组。例如，您可以根据当前的搜索文本更新补全。请注意，某些事件或操作（例如移动 macOS 窗口）可能会导致建议视图关闭。

有关使用搜索修饰符的更多信息，请参阅 [Adding-a-search-interface-to-your-app](../Adding-a-search-interface-to-your-app.zh-Hans.md)。

## 生成搜索建议

- **建议搜索词**：为在您的应用中搜索内容的用户提供建议。

- **searchSuggestions(_:for:)**：配置如何在此视图中显示搜索建议。

- **searchCompletion(_:)**：将一个完整的字符串与此视图的值关联起来，以便用作搜索建议。

- **searchable(text:tokens:suggestedTokens:placement:prompt:token:)**：将此视图标记为可搜索，支持文本、标记和建议。

- **SearchSuggestionsPlacement**：SwiftUI 显示搜索建议的方式。


---
source: https://developer.apple.com/documentation/SwiftUI/View/searchSuggestions(_:)
crawled: 2025-12-02T17:31:36Z
---

# searchSuggestions(_:)

**Instance Method**

Configures the search suggestions for this view.

## Declaration

```swift
nonisolated func searchSuggestions<S>(@ViewBuilder _ suggestions: () -> S) -> some View where S : View

```

## Parameters

- **suggestions**: A view builder that produces content that populates a list of suggestions.

## Discussion

You can suggest search terms during a search operation by providing a collection of view to this modifier. The interface presents the suggestion views as a list of choices when someone activates the search interface. Associate a string with each suggestion view by adding the [searchCompletion(_:)](searchCompletion.zh-Hans.md) modifier to the view. For example, you can suggest fruit types by displaying their emoji, and provide the corresponding search string as a search completion in each case:

```swift
ProductList()
    .searchable(text: $text)
    .searchSuggestions {
        Text("🍎").searchCompletion("apple")
        Text("🍐").searchCompletion("pear")
        Text("🍌").searchCompletion("banana")
    }
```

When someone chooses a suggestion, SwiftUI replaces the text in the search field with the search completion string. If you omit the search completion modifier for a particular suggestion view, SwiftUI displays the suggestion, but the suggestion view doesn’t react to taps or clicks.



You can update the suggestions that you provide as conditions change.

For example, you can specify an array of suggestions that you store in a model:

```swift
ProductList()
    .searchable(text: $text)
    .searchSuggestions {
        ForEach(model.suggestedSearches) { suggestion in
            Label(suggestion.title, image: suggestion.image)
                .searchCompletion(suggestion.text)
        }
    }
```

If the model’s `suggestedSearches` begins as an empty array, the interface doesn’t display any suggestions to start. You can then provide logic that updates the array based on some condition. For example, you might update the completions based on the current search text. Note that certain events or actions, like when someone moves a macOS window, might dismiss the suggestion view.

For more information about using search modifiers, see [Adding-a-search-interface-to-your-app](../Adding-a-search-interface-to-your-app.zh-Hans.md).

## Making search suggestions

- **Suggesting search terms**: Provide suggestions to people searching for content in your app.
- **searchSuggestions(_:for:)**: Configures how to display search suggestions within this view.
- **searchCompletion(_:)**: Associates a fully formed string with the value of this view when used as a search suggestion.
- **searchable(text:tokens:suggestedTokens:placement:prompt:token:)**: Marks this view as searchable with text, tokens, and suggestions.
- **SearchSuggestionsPlacement**: The ways that SwiftUI displays search suggestions.

