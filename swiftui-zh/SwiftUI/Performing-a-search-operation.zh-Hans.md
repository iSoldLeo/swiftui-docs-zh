--- 来源：https://developer.apple.com/documentation/SwiftUI/Performing-a-search-operation

抓取时间：2025-12-02T17:31:32Z

---

# 执行搜索操作

**Article**

根据搜索文本和您存储的可选标记更新搜索结果。

## 概述

要在应用的数据模型中执行搜索，请创建用于存储查询文本的存储空间，并使用可搜索视图修饰符显示它。由于您可以管理存储空间，因此可以检测到其更改并相应地更新搜索操作。通过在用户输入时更新搜索结果，您可以确保应用的搜索界面具有响应性。

您还可以选择提供用于存储标记的存储空间，标记是应用识别的离散搜索词。标记提供了一种组合多个搜索词的方法，并使您更容易指示某个搜索词在您的应用中是常用的或预期的。

有关如何控制搜索字段在应用界面中的位置，请参阅 [Adding-a-search-interface-to-your-app](Adding-a-search-interface-to-your-app.zh-Hans.md)。

### 提供字符串存储

可搜索修饰符接受一个 [Binding](Binding.zh-Hans.md) 到 `text` 输入的字符串值。该字符串用作 SwiftUI 显示的搜索查询字段的存储内容。您可以使用 [State](State.zh-Hans.md) 属性在视图中创建此存储，并将其初始化为空字符串：

```swift
@State private var searchText: String = ""
```

为了更方便地在不同视图之间共享搜索查询，您可以在应用程序模型中的可观察对象内创建一个已发布值：

```swift
class Model: ObservableObject {
    @Published var searchText: String = ""
}
```

无论哪种情况，都可以通过在值前添加美元符号 (`$`) 前缀，将 [Binding](Binding.zh-Hans.md) 传递给可搜索视图修饰符：

```swift
struct ContentView: View {
    @EnvironmentObject private var model: Model
    @State private var departmentId: Department.ID?
    @State private var productId: Product.ID?

    var body: some View {
        NavigationSplitView {
            DepartmentList(departmentId: $departmentId)
        } content: {
            ProductList(departmentId: departmentId, productId: $productId)
                .searchable(text: $model.searchText)
        } detail: {
            ProductDetails(productId: productId)
        }
    }
}
```

### 提供令牌存储

除了搜索字符串之外，当您使用带有 `tokens` 参数的可搜索修饰符（例如 [searchable(text:tokens:placement:prompt:token:)](View/searchable_text_tokens_placement_prompt_token.zh-Hans.md)）时，搜索字段还可以显示令牌。

创建令牌的方法是定义一组符合 [doc://com.apple.documentation/documentation/Swift/Identifiable] 协议的值，然后实例化该值集合。例如，您可以创建一个水果令牌枚举：

```swift
enum FruitToken: String, Identifiable, Hashable, CaseIterable {
    case apple
    case pear
    case banana
    var id: Self { self }
}
```

然后，向您的模型添加一个新的已发布属性来存储令牌集合：

```swift
@Published var tokens: [FruitToken] = []
```

要显示令牌，请将 [Binding](Binding.zh-Hans.md) 作为可搜索修饰符的 `tokens` 输入参数提供给 `tokens` 数组，并使用 `token` 闭包描述如何绘制每个令牌。从闭包中，返回表示作为输入给定的令牌的 [View](View.zh-Hans.md)。例如，您可以使用 [Text](Text.zh-Hans.md) 视图来表示每个词元：

```swift
ProductList(departmentId: departmentId, productId: $productId)
    .searchable(text: $model.searchText, tokens: $model.tokens) { token in
        switch token {
        case .apple: Text("Apple")
        case .pear: Text("Pear")
        case .banana: Text("Banana")
        }
    }
```

您可以使用 [Text](Text.zh-Hans.md) 视图来表示词元，如上例所示。在 iOS 和 iPadOS 中，您可以使用 [Label](Label.zh-Hans.md) 视图。请确保视图清晰地表示相应的搜索查询，并且如果您使用标签，请确保词元的高度与搜索查询字段的高度相匹配。词元会显示在搜索字段的开头，位于所有纯文本之前。以下示例展示了当 `tokens` 数组包含 `apple` 和 `banana` 标记时，搜索字段的显示方式：

### 支持包含可变组件的标记

您可以通过在 `token` 闭包中使用 [Picker](Picker.zh-Hans.md) 来允许用户修改表示标记的部分数据。例如，假设您有一个水果标记数据，其中包含种类 (kind) 和水合度 (hydration) 属性：

```swift
struct FruitToken: String, Identifiable, Hashable, CaseIterable {
    enum Kind {
        case apple
        case pear
        case banana
        var id: Self { self }
    }

    enum Hydration: String, Identifiable, Hashable, CaseIterable {
        case hydrated
        case dehydrated
    }

    var kind: Kind
    var hydration: Hydration = .hydrated
}
```

在您的新模型中，通过在 `token` 闭包中添加美元符号 (`$`) 来为标记指定 [Binding](Binding.zh-Hans.md)。使用绑定为 `hydration` 属性创建一个选择器，并为 `kind` 属性创建一个标签：

```swift
ProductList(departmentId: departmentId, productId: $productId)
    .searchable(text: $model.searchText, tokens: $model.tokens) { $token in
        Picker(selection: $token.hydration) {
            ForEach(FruitToken.Hydration.allCases) { hydration in
                switch hydration {
                case .hydrated: Text("Hydrated")
                case .dehydrated: Text("Dehydrated")
                }
            }
        } label: {
            switch token.kind {
            case .apple: Text("Apple")
            case .pear: Text("Pear")
            case .banana: Text("Banana")
            }
        }
    }
```

### 向搜索添加标记

提供一种让用户向搜索字段添加标记的方法。您可以通过多种方式实现。例如：

- 使用具有 `suggestedTokens` 输入参数的可搜索视图修饰符（例如 [searchable(text:tokens:suggestedTokens:placement:prompt:token:)](View/searchable_text_tokens_suggestedTokens_placement_prompt_token.zh-Hans.md)）来建议要添加到数组中的标记。用户可以从搜索字段下方显示的列表中选择建议。有关提供标记和搜索文本建议的更多信息，请参阅 [Suggesting-search-terms](Suggesting-search-terms.zh-Hans.md)。

- 监控用户编辑搜索字符串的过程。当检测到与某个标记匹配的子字符串时，通过从字符串中移除相关字符将文本转换为标记，并将相应的标记添加到 `tokens` 数组中。

- 等待搜索字符串中出现分隔符（例如逗号或空格），然后尝试对前面的字符进行标记化。

- 等待用户提交搜索，然后尝试对整个搜索字符串进行标记化。有关提交搜索的更多信息，请参阅 [Managing-search-interface-activation](Managing-search-interface-activation.zh-Hans.md)。

### 执行搜索

当检测到搜索查询发生变化时，您的应用可以开始搜索。执行搜索操作的方式取决于您的应用如何存储和呈现数据。一种方法是根据列表项中的字段是否与搜索查询匹配来过滤 [List](List.zh-Hans.md) 中显示的元素。例如，您可以创建一个方法，该方法仅返回产品数组中名称与搜索文本或当前搜索字段中的某个标记匹配的项：

```swift
func filteredProducts(
    products: [Product],
    searchText: String,
    tokens: [FruitToken]
) -> [Product] {
    guard !searchText.isEmpty || !tokens.isEmpty else { return products }
    return products.filter { product in
        product.name.lowercased().contains(searchText.lowercased()) ||
        tokens.map({ $0.rawValue }).contains(product.name.lowercased())
    }
}
```

考虑搜索的复杂性和更改搜索词的成本。如果成本很高，例如更新需要网络访问或使用复杂的过滤逻辑，请考虑预取和缓存数据或降低更新频率。或者，您可以等待用户提交查询后再执行搜索。有关检测查询提交的信息，请参阅 [Managing-search-interface-activation](Managing-search-interface-activation.zh-Hans.md)。

如果搜索范围可以划分为多个大类，您可以通过提供搜索范围来帮助用户更快地缩小搜索范围。请参阅 [Scoping-a-search-operation](Scoping-a-search-operation.zh-Hans.md)。

## 搜索应用的数据模型

- **向应用添加搜索界面**：提供一个界面，供用户搜索应用中的内容。

- **searchable(text:placement:prompt:)**：将此视图标记为可搜索，这将配置搜索字段的显示。

- **searchable(text:tokens:placement:prompt:token:)**：将此视图标记为可使用文本和标记进行搜索。

- **searchable(text:editableTokens:placement:prompt:token:)**：将此视图标记为可搜索，这将配置搜索字段的显示。

- **SearchFieldPlacement**：在视图层次结构中定位搜索字段。


---
source: https://developer.apple.com/documentation/SwiftUI/Performing-a-search-operation
crawled: 2025-12-02T17:31:32Z
---

# Performing a search operation

**Article**

Update search results based on search text and optional tokens that you store.

## Overview

To conduct a search in your app’s data model, create storage for the query text and present it with a searchable view modifier. Because you manage the storage, you can detect when it changes and update the search operation in response. By updating search results as people type, you ensure that your app’s search interface is responsive.

You can also optionally provide storage for tokens, which are discrete search terms that your app recognizes. Tokens provide a way to combine multiple search terms, and make it easier for you to indicate that a search term is common or expected in your app.



For information on how to control the placement of the search field in your app’s interface, see [Adding-a-search-interface-to-your-app](Adding-a-search-interface-to-your-app.zh-Hans.md).

### Provide storage for a string

The searchable modifiers take a [Binding](Binding.zh-Hans.md) to a string value for the `text` input. The string serves as the storage for the search query field that SwiftUI displays. You can create this storage inside a view using a [State](State.zh-Hans.md) property, and initialize it to an empty string:

```swift
@State private var searchText: String = ""
```

To make it easier to share the search query among different views, you can create a published value inside an observable object that’s part of your app’s model:

```swift
class Model: ObservableObject {
    @Published var searchText: String = ""
}
```

In either case, pass a [Binding](Binding.zh-Hans.md) to this string into the searchable view modifier by adding the dollar sign (`$`) prefix to the value:

```swift
struct ContentView: View {
    @EnvironmentObject private var model: Model
    @State private var departmentId: Department.ID?
    @State private var productId: Product.ID?

    var body: some View {
        NavigationSplitView {
            DepartmentList(departmentId: $departmentId)
        } content: {
            ProductList(departmentId: departmentId, productId: $productId)
                .searchable(text: $model.searchText)
        } detail: {
            ProductDetails(productId: productId)
        }
    }
}
```

### Provide storage for tokens

In addition to a search string, the search field can also display tokens when you use one of the searchable modifiers that has a `tokens` parameter, like [searchable(text:tokens:placement:prompt:token:)](View/searchable_text_tokens_placement_prompt_token.zh-Hans.md).

You create tokens by defining a group of values that conform to the [doc://com.apple.documentation/documentation/Swift/Identifiable] protocol, then instantiate the collection of values. For example you can create an enumeration of fruit tokens:

```swift
enum FruitToken: String, Identifiable, Hashable, CaseIterable {
    case apple
    case pear
    case banana
    var id: Self { self }
}
```

Then add a new published property to your model to store a collection of tokens:

```swift
@Published var tokens: [FruitToken] = []
```

To display tokens, provide a [Binding](Binding.zh-Hans.md) to the `tokens` array as the searchable modifier’s `tokens` input parameter, and describe how to draw each token using the `token` closure. From the closure, return the [View](View.zh-Hans.md) that represents the token given as an input. For example, you can use a [Text](Text.zh-Hans.md) view to represent each token:

```swift
ProductList(departmentId: departmentId, productId: $productId)
    .searchable(text: $model.searchText, tokens: $model.tokens) { token in
        switch token {
        case .apple: Text("Apple")
        case .pear: Text("Pear")
        case .banana: Text("Banana")
        }
    }
```

You can represent the token with a [Text](Text.zh-Hans.md) view, as the above example demonstrates. In iOS and iPadOS, you can use a [Label](Label.zh-Hans.md) instead. Ensure the view clearly represents the corresponding search query, and if you use a label, that the tokens fit the search query field’s height. Tokens appear at the beginning of the search field before any plain text. The following shows how the search field looks when the `tokens` array contains the `apple` and `banana` tokens:



### Support tokens that have a mutable component

You can enable people to mutate part of the data that represents a token by using a [Picker](Picker.zh-Hans.md) in the `token` closure. For example, suppose you have fruit token data that contains both a kind and a hydration property:

```swift
struct FruitToken: String, Identifiable, Hashable, CaseIterable {
    enum Kind {
        case apple
        case pear
        case banana
        var id: Self { self }
    }

    enum Hydration: String, Identifiable, Hashable, CaseIterable {
        case hydrated
        case dehydrated
    }

    var kind: Kind
    var hydration: Hydration = .hydrated
}
```

With your new model, specify a [Binding](Binding.zh-Hans.md) to the token in the `token` closure by adding a dollar sign (`$`). Use the binding to create a picker for the `hydration` property and a label that uses the `kind` property:

```swift
ProductList(departmentId: departmentId, productId: $productId)
    .searchable(text: $model.searchText, tokens: $model.tokens) { $token in
        Picker(selection: $token.hydration) {
            ForEach(FruitToken.Hydration.allCases) { hydration in
                switch hydration {
                case .hydrated: Text("Hydrated")
                case .dehydrated: Text("Dehydrated")
                }
            }
        } label: {
            switch token.kind {
            case .apple: Text("Apple")
            case .pear: Text("Pear")
            case .banana: Text("Banana")
            }
        }
    }
```

### Add tokens to the search

Provide a way for people to add tokens to the search field. You can do this in different ways. For example, you can:

- Suggest tokens to add to the array by using one of the searchable view modifiers that have a `suggestedTokens` input parameter, like [searchable(text:tokens:suggestedTokens:placement:prompt:token:)](View/searchable_text_tokens_suggestedTokens_placement_prompt_token.zh-Hans.md). People select suggestions from a list that appears below the search field. For more information about offering suggestions for tokens, as well as for search text, see [Suggesting-search-terms](Suggesting-search-terms.zh-Hans.md).
- Monitor the search string as people edit it. When you detect a substring that matches one of the tokens, convert the text into a token by removing the relevant characters from the string and add the corresponding token to the `tokens` array.
- Wait until you see a dividing character in the search string, like a comma or a space, and then attempt to tokenize the preceding characters.
- Wait until someone submits the search, and then attempt to tokenize the entire search string. For more information about submitting a search, see [Managing-search-interface-activation](Managing-search-interface-activation.zh-Hans.md).

### Conduct the search

When you detect changes in the search query, your app can begin a search. How you perform the search operation depends on how your app stores and presents data. One approach is to filter the elements that appear in a [List](List.zh-Hans.md) based on whether a field in the list’s items matches the search query. For example, you can create a method that returns only the items in an array of products with names that match the search text or one of the tokens currently in the search field:

```swift
func filteredProducts(
    products: [Product],
    searchText: String,
    tokens: [FruitToken]
) -> [Product] {
    guard !searchText.isEmpty || !tokens.isEmpty else { return products }
    return products.filter { product in
        product.name.lowercased().contains(searchText.lowercased()) ||
        tokens.map({ $0.rawValue }).contains(product.name.lowercased())
    }
}
```

Consider the complexity of the search and the cost of changing the search terms. If the cost is high, like when updates require network access, or for complex filter logic, consider prefetching and caching data or reducing the frequency of updates. Alternatively, you can wait until someone submits the query before conducting the search. For information about detecting query submission, see [Managing-search-interface-activation](Managing-search-interface-activation.zh-Hans.md).

If the search space can be broken into broad categories, you can help people narrow the search more quickly by providing a scope. See [Scoping-a-search-operation](Scoping-a-search-operation.zh-Hans.md).

## Searching your app’s data model

- **Adding a search interface to your app**: Present an interface that people can use to search for content in your app.
- **searchable(text:placement:prompt:)**: Marks this view as searchable, which configures the display of a search field.
- **searchable(text:tokens:placement:prompt:token:)**: Marks this view as searchable with text and tokens.
- **searchable(text:editableTokens:placement:prompt:token:)**: Marks this view as searchable, which configures the display of a search field.
- **SearchFieldPlacement**: The placement of a search field in a view hierarchy.

