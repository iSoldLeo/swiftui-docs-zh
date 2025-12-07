--- 来源：https://developer.apple.com/documentation/SwiftUI/View/searchScopes(_:activation:_:)

抓取时间：2025-12-02T17:31:43Z

---

# searchScopes(_:activation:_:)

**实例方法**

使用指定的激活策略配置此视图的搜索范围。

## 声明

```swift
nonisolated func searchScopes<V, S>(_ scope: Binding<V>, activation: SearchScopeActivation, @ViewBuilder _ scopes: () -> S) -> some View where V : Hashable, S : View

```

## 参数

- **scope**：搜索字段的激活范围。

- **activation**：搜索字段范围的激活样式。

- **scopes**：一个视图构建器，表示 SwiftUI 用于填充 [Picker](../Picker.zh-Hans.md) 的范围选项。

## 讨论

为了让用户能够缩小搜索范围，您可以创建一个类型来表示所有可能的范围，然后创建一个状态变量来保存当前的选择。例如，您可以将产品搜索范围限定为水果或蔬菜：

```swift
enum ProductScope {
    case fruit
    case vegetable
}

@State private var scope: ProductScope = .fruit
```

为范围提供一个绑定，以及一个表示每个范围的视图：

```swift
ProductList()
    .searchable(text: $text, tokens: $tokens) { token in
        switch token {
        case .apple: Text("Apple")
        case .pear: Text("Pear")
        case .banana: Text("Banana")
        }
    }
    .searchScopes($scope) {
        Text("Fruit").tag(ProductScope.fruit)
        Text("Vegetable").tag(ProductScope.vegetable)
    }
```

SwiftUI 使用此绑定和视图在搜索框下方添加一个 [Picker](../Picker.zh-Hans.md) 选择器。在 iOS、macOS 和 tvOS 中，当搜索处于活动状态时，选择器会显示在搜索框下方。为了确保选择器正常工作，请将范围绑定的类型与每个视图标签的类型匹配。然后，根据 `scope` 状态属性的当前值来设置搜索条件。

默认情况下，搜索范围的显示方式因平台而异：

- 在 iOS 和 iPadOS 中，当用户在搜索框中输入文本时，搜索范围会显示；当用户取消搜索时，搜索范围会消失。

- 在 macOS 中，当 SwiftUI 显示搜索框时，搜索范围会显示；当用户取消搜索时，搜索范围会消失。

但是，您可以使用参数 `activation` 并将其值设置为 [onTextEntry](../SearchScopeActivation/onTextEntry.zh-Hans.md) 或 [onSearchPresentation](../SearchScopeActivation/onSearchPresentation.zh-Hans.md) 来配置此行为：

```swift
.searchScopes($scope, activation: .onSearchPresentation) {
    Text("Fruit").tag(ProductScope.fruit)
    Text("Vegetable").tag(ProductScope.vegetable)
}
```

有关使用可搜索修饰符的更多信息，请参阅 [Adding-a-search-interface-to-your-app](../Adding-a-search-interface-to-your-app.zh-Hans.md)。

## 限制搜索范围

- **限定搜索操作范围**：将搜索空间划分为几个大类。

- **searchScopes(_:scopes:)**：配置此视图的搜索范围。

- **SearchScopeActivation**：可搜索修饰符显示或隐藏搜索范围的方式。


---
source: https://developer.apple.com/documentation/SwiftUI/View/searchScopes(_:activation:_:)
crawled: 2025-12-02T17:31:43Z
---

# searchScopes(_:activation:_:)

**Instance Method**

Configures the search scopes for this view with the specified activation strategy.

## Declaration

```swift
nonisolated func searchScopes<V, S>(_ scope: Binding<V>, activation: SearchScopeActivation, @ViewBuilder _ scopes: () -> S) -> some View where V : Hashable, S : View

```

## Parameters

- **scope**: The active scope of the search field.
- **activation**: The activation style of the search field’s scopes.
- **scopes**: A view builder that represents the scoping options SwiftUI uses to populate a [Picker](../Picker.zh-Hans.md).

## Discussion

To enable people to narrow the scope of their searches, you can create a type that represents the possible scopes, and then create a state variable to hold the current selection. For example, you can scope the product search to just fruits or just vegetables:

```swift
enum ProductScope {
    case fruit
    case vegetable
}

@State private var scope: ProductScope = .fruit
```

Provide a binding to the scope, as well as a view that represents each scope:

```swift
ProductList()
    .searchable(text: $text, tokens: $tokens) { token in
        switch token {
        case .apple: Text("Apple")
        case .pear: Text("Pear")
        case .banana: Text("Banana")
        }
    }
    .searchScopes($scope) {
        Text("Fruit").tag(ProductScope.fruit)
        Text("Vegetable").tag(ProductScope.vegetable)
    }
```

SwiftUI uses this binding and view to add a [Picker](../Picker.zh-Hans.md) below the search field. In iOS, macOS, and tvOS, the picker appears below the search field when search is active. To ensure that the picker operates correctly, match the type of the scope binding with the type of each view’s tag. Then condition your search on the current value of the `scope` state property.

By default, the appearance of scopes varies by platform:

- In iOS and iPadOS, search scopes appear when someone enters text into the search field and disappear when someone cancels the search.
- In macOS, search scopes appear when SwiftUI presents search and disappear when someone cancels the search.

However, you can use the `activation` parameter with a value of [onTextEntry](../SearchScopeActivation/onTextEntry.zh-Hans.md) or [onSearchPresentation](../SearchScopeActivation/onSearchPresentation.zh-Hans.md) to configure this behavior:

```swift
.searchScopes($scope, activation: .onSearchPresentation) {
    Text("Fruit").tag(ProductScope.fruit)
    Text("Vegetable").tag(ProductScope.vegetable)
}
```

For more information about using searchable modifiers, see [Adding-a-search-interface-to-your-app](../Adding-a-search-interface-to-your-app.zh-Hans.md).

## Limiting search scope

- **Scoping a search operation**: Divide the search space into a few broad categories.
- **searchScopes(_:scopes:)**: Configures the search scopes for this view.
- **SearchScopeActivation**: The ways that searchable modifiers can show or hide search scopes.

