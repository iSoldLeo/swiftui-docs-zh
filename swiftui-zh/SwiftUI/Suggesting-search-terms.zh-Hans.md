--- 来源：https://developer.apple.com/documentation/SwiftUI/Suggesting-search-terms

抓取时间：2025-12-02T17:31:35Z

---

# 搜索词建议

**Article**

为在您的应用中搜索内容的用户提供建议。

## 概述

您可以通过提供一系列搜索建议视图，在搜索操作期间提供查询文本建议。由于建议视图不限于纯文本，因此您还必须提供每个建议视图所代表的搜索字符串。如果您的搜索界面支持词元，您也可以提供词元建议。SwiftUI 会将建议显示在搜索字段下方的列表中。

对于文本和词元，您都可以管理建议列表，因此您可以完全灵活地决定建议的内容。例如，您可以：

- 提供静态建议列表。

- 记住之前的搜索记录，并提供最近或最常用的搜索词。

- 根据当前搜索文本实时更新建议列表。

- 采用这些策略以及其他策略的组合，并可能随时间推移而变化。

### 建议搜索文本

通过向 [searchSuggestions(_:)](View/searchSuggestions.zh-Hans.md) 视图修饰符提供一系列视图来建议搜索文本。此修饰符应用于其前面的 [searchable(text:placement:prompt:)](View/searchable_text_placement_prompt.zh-Hans.md) 修饰符。

当用户激活搜索界面时，它会在查询字符串下方显示建议视图列表。通过在搜索建议闭包内向视图添加 [searchCompletion(_:)](View/searchCompletion.zh-Hans.md) 修饰符，将字符串与每个建议视图关联起来。例如，您可以将表情符号与您建议的可能搜索的水果类型一起添加，并在每种情况下提供相应的搜索字符串作为搜索补全：

```swift
ProductList(departmentId: departmentId, productId: $productId)
    .searchable(text: $model.searchText)
    .searchSuggestions {
        Text("🍎 Apple").searchCompletion("apple")
        Text("🍐 Pear").searchCompletion("pear")
        Text("🍌 Banana").searchCompletion("banana")
    }
```

当用户选择建议时，SwiftUI 会将搜索字段中的文本替换为搜索补全字符串。在上面的示例中，选择“🍐 梨”会将文本“梨”添加到搜索查询中。

如果您省略了特定建议视图的搜索完成修饰符，SwiftUI 会显示该视图，但该视图不会响应点击或轻触操作。不过，您可以使用带有标题的 [Section](Section.zh-Hans.md) 容器对视图进行分组，从而区分不同类型的建议，例如最近的搜索和常用搜索词。

某些事件或操作（例如用户移动 macOS 窗口）可能会关闭建议列表。

### 建议令牌

您还可以为搜索字段建议令牌。在这种情况下，请使用接受令牌作为输入的 [searchCompletion(_:)](View/searchCompletion.zh-Hans.md) 修饰符版本将建议视图与令牌关联起来：

```swift
ProductList(departmentId: departmentId, productId: $productId)
    .searchable(text: $model.searchText, tokens: $model.tokens) { token in
        switch token {
        case .apple: Text("Apple")
        case .pear: Text("Pear")
        case .banana: Text("Banana")
        }
    }
    .searchSuggestions {
        Text("Apple").searchCompletion(FruitToken.apple)
        Text("Pear").searchCompletion(FruitToken.pear)
        Text("Banana").searchCompletion(FruitToken.banana)
    }
```

您可以使用任何符合 [doc://com.apple.documentation/documentation/Swift/Identifiable] 协议的类型作为令牌。有关在搜索查询中使用标记的更多信息，请参阅 [Performing-a-search-operation](Performing-a-search-operation.zh-Hans.md)。

### 简化标记建议

为了方便起见，当您有一组与标记列表完全匹配的建议时，可以创建一个包含所有可能建议标记的集合。例如，您可以向模型添加一个已发布的 `suggestions` 属性，其中包含所有可能的标记：

```swift
@Published var suggestions: [FruitToken] = FruitToken.allCases
```

然后，您可以将此数组提供给接受 `suggestedTokens` 输入参数的可搜索修饰符，例如 [searchable(text:tokens:suggestedTokens:placement:prompt:token:)](View/searchable_text_tokens_suggestedTokens_placement_prompt_token.zh-Hans.md)。SwiftUI 使用此数组自动生成建议：

```swift
ProductList(departmentId: departmentId, productId: $productId)
    .searchable(
        text: $model.searchText,
        tokens: $model.tokens,
        suggestedTokens: $model.suggestions
    ) { token in
        switch token {
        case .apple: Text("Apple")
        case .pear: Text("Pear")
        case .banana: Text("Banana")
        }
    }
```

在此版本的可搜索修饰符中，SwiftUI 使用同一个视图构建器来描述标记在搜索字段和建议容器中的显示方式。

### 动态更新建议

您可以根据条件的变化更新提供的建议。例如，您可以指定一个数组 `suggestedSearches`，并将其存储在应用程序的模型中：

```swift
ProductList(departmentId: departmentId, productId: $productId)
    .searchable(text: $model.searchText)
    .searchSuggestions {
        ForEach(model.suggestedSearches) { suggestion in
            Label(suggestion.title,  image: suggestion.image)
                .searchCompletion(suggestion.text)
        }
    }
```

如果 `suggestedSearches` 初始为空数组，则界面最初不会显示任何建议。您可以根据条件的变化更新该数组，例如，当您想要包含之前的搜索记录时。

## 创建搜索建议

- **searchSuggestions(_:)**：配置此视图的搜索建议。

- **searchSuggestions(_:for:)**：配置如何在此视图中显示搜索建议。

- **searchCompletion(_:)**：将一个完整的字符串与此视图的值关联起来，以便用作搜索建议。

- **searchable(text:tokens:suggestedTokens:placement:prompt:token:)**：将此视图标记为可搜索，支持文本、词条和搜索建议。

- **SearchSuggestionsPlacement**：SwiftUI 显示搜索建议的方式。


---
source: https://developer.apple.com/documentation/SwiftUI/Suggesting-search-terms
crawled: 2025-12-02T17:31:35Z
---

# Suggesting search terms

**Article**

Provide suggestions to people searching for content in your app.

## Overview

You can suggest query text during a search operation by providing a collection of search suggestion views. Because suggestion views are not limited to plain text, you must also provide the search string that each suggestion view represents. You can also provide suggestions for tokens, if your search interface includes them. SwiftUI presents the suggestions in a list below the search field.



For both text and tokens, you manage the list of suggestions, so you have complete flexibility to decide what to suggest. For example, you can:

- Offer a static list of suggestions.
- Remember previous searches and offer the most recent or most common ones.
- Update the list of suggestions in real time based on the current search text.
- Employ some combination of these and other strategies, possibly changing over time.

### Suggest search text

Suggest search text by providing a collection of views to the [searchSuggestions(_:)](View/searchSuggestions.zh-Hans.md) view modifier. This modifier applies to the [searchable(text:placement:prompt:)](View/searchable_text_placement_prompt.zh-Hans.md) modifier that appears before it.

When someone activates the search interface, it presents the suggestion views as a list of choices below the query string. Associate a string with each suggestion view by adding the [searchCompletion(_:)](View/searchCompletion.zh-Hans.md) modifier to the view inside the search suggestions closure. For example, you can include emoji with fruit types that you suggest as possible products to search for, and provide the corresponding search string as a search completion in each case:

```swift
ProductList(departmentId: departmentId, productId: $productId)
    .searchable(text: $model.searchText)
    .searchSuggestions {
        Text("🍎 Apple").searchCompletion("apple")
        Text("🍐 Pear").searchCompletion("pear")
        Text("🍌 Banana").searchCompletion("banana")
    }
```

When someone chooses a suggestion, SwiftUI replaces the text in the search field with the search completion string. In the above example, choosing “🍐 Pear” puts the text “pear” in the search query.



If you omit the search completion modifier for a particular suggestion view, SwiftUI displays the view, but the view doesn’t react to taps or clicks. However, you can group the views with [Section](Section.zh-Hans.md) containers that have headers, enabling you to distinguish different kinds of suggestions, like recent searches and common search terms.



Certain events or actions, like when someone moves a macOS window, might dismiss the suggestion list.

### Suggest tokens

You can also suggest tokens for the search field. In this case, associate a suggestion view with a token using the version of the [searchCompletion(_:)](View/searchCompletion.zh-Hans.md) modifier that takes tokens as input:

```swift
ProductList(departmentId: departmentId, productId: $productId)
    .searchable(text: $model.searchText, tokens: $model.tokens) { token in
        switch token {
        case .apple: Text("Apple")
        case .pear: Text("Pear")
        case .banana: Text("Banana")
        }
    }
    .searchSuggestions {
        Text("Apple").searchCompletion(FruitToken.apple)
        Text("Pear").searchCompletion(FruitToken.pear)
        Text("Banana").searchCompletion(FruitToken.banana)
    }
```

You can use any type that conforms to the [doc://com.apple.documentation/documentation/Swift/Identifiable] protocol as a token. For more information about using tokens in the search query, see [Performing-a-search-operation](Performing-a-search-operation.zh-Hans.md).

### Simplify token suggestions

As a convenience when you have a collection of suggestions that exactly matches the list of tokens, you can create a collection of possible tokens to suggest. For example, you can add a published `suggestions` property to your model that contains all the possible tokens:

```swift
@Published var suggestions: [FruitToken] = FruitToken.allCases
```

Then you can provide this array to one of the searchable modifiers that takes a `suggestedTokens` input parameter, like [searchable(text:tokens:suggestedTokens:placement:prompt:token:)](View/searchable_text_tokens_suggestedTokens_placement_prompt_token.zh-Hans.md). SwiftUI uses this to generate the suggestions automatically:

```swift
ProductList(departmentId: departmentId, productId: $productId)
    .searchable(
        text: $model.searchText,
        tokens: $model.tokens,
        suggestedTokens: $model.suggestions
    ) { token in
        switch token {
        case .apple: Text("Apple")
        case .pear: Text("Pear")
        case .banana: Text("Banana")
        }
    }
```

In this version of the searchable modifier, SwiftUI uses one view builder to describe the appearance of the tokens in both the search field and the suggestions container.

### Update suggestions dynamically

You can update the suggestions that you provide as conditions change. For example, you can specify an array of `suggestedSearches` that you store in your app’s model:

```swift
ProductList(departmentId: departmentId, productId: $productId)
    .searchable(text: $model.searchText)
    .searchSuggestions {
        ForEach(model.suggestedSearches) { suggestion in
            Label(suggestion.title,  image: suggestion.image)
                .searchCompletion(suggestion.text)
        }
    }
```

If `suggestedSearches` begins as an empty array, the interface doesn’t display any suggestions to start. You can then update the array as conditions change, like when you want to include previous searches.

## Making search suggestions

- **searchSuggestions(_:)**: Configures the search suggestions for this view.
- **searchSuggestions(_:for:)**: Configures how to display search suggestions within this view.
- **searchCompletion(_:)**: Associates a fully formed string with the value of this view when used as a search suggestion.
- **searchable(text:tokens:suggestedTokens:placement:prompt:token:)**: Marks this view as searchable with text, tokens, and suggestions.
- **SearchSuggestionsPlacement**: The ways that SwiftUI displays search suggestions.

