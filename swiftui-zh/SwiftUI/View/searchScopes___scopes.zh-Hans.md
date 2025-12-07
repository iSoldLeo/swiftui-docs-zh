--- 来源：https://developer.apple.com/documentation/SwiftUI/View/searchScopes(_:scopes:)

抓取时间：2025-11-30T21:16:47Z

---

# searchScopes(_:scopes:)

**实例方法**

配置此视图的搜索范围。

## 声明

```swift
nonisolated func searchScopes<V, S>(_ scope: Binding<V>, @ViewBuilder scopes: () -> S) -> some View where V : Hashable, S : View

```

## 参数

- **scope**：搜索字段的活动范围。

- **scopes**：一个视图构建器，表示 SwiftUI 用于填充 [Picker](../Picker.zh-Hans.md) 的范围选项。

## 讨论

为了方便用户缩小搜索范围，您可以创建一个表示所有可能范围的类型，然后创建一个状态变量来保存当前选择。例如，您可以将产品搜索范围限定为水果或蔬菜：

```swift
enum ProductScope {
    case fruit
    case vegetable
}

@State private var scope: ProductScope = .fruit
```

为搜索范围提供一个绑定，以及一个代表每个搜索范围的视图：

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

SwiftUI 使用此绑定和视图在搜索字段中添加一个 [Picker](../Picker.zh-Hans.md) 选择器。在 iOS、iPadOS、macOS 和 tvOS 中，搜索激活时，选择器会显示在搜索字段下方。为确保选择器正常工作，请将搜索范围绑定的类型与每个视图的标签类型匹配。然后，修改您的搜索以适应 `scope` 状态属性的当前值。

有关使用可搜索修饰符的更多信息，请参阅 [Adding-a-search-interface-to-your-app](../Adding-a-search-interface-to-your-app.zh-Hans.md)。

## 限制搜索范围

- **限定搜索操作的范围**：将搜索空间划分为几个大类。

- **searchScopes(_:activation:_:)**：使用指定的激活策略配置此视图的搜索范围。

- **SearchScopeActivation**：可搜索修饰符显示或隐藏搜索范围的方式。


---
source: https://developer.apple.com/documentation/SwiftUI/View/searchScopes(_:scopes:)
crawled: 2025-11-30T21:16:47Z
---

# searchScopes(_:scopes:)

**Instance Method**

Configures the search scopes for this view.

## Declaration

```swift
nonisolated func searchScopes<V, S>(_ scope: Binding<V>, @ViewBuilder scopes: () -> S) -> some View where V : Hashable, S : View

```

## Parameters

- **scope**: The active scope of the search field.
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

SwiftUI uses this binding and view to add a [Picker](../Picker.zh-Hans.md) with the search field. In iOS, iPadOS, macOS, and tvOS, the picker appears below the search field when search is active. To ensure that the picker operates correctly, match the type of the scope binding with the type of each view’s tag. Then modify your search to account for the current value of the `scope` state property.

For more information about using searchable modifiers, see [Adding-a-search-interface-to-your-app](../Adding-a-search-interface-to-your-app.zh-Hans.md).

## Limiting search scope

- **Scoping a search operation**: Divide the search space into a few broad categories.
- **searchScopes(_:activation:_:)**: Configures the search scopes for this view with the specified activation strategy.
- **SearchScopeActivation**: The ways that searchable modifiers can show or hide search scopes.

