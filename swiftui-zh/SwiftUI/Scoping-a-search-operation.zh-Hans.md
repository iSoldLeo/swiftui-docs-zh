---
来源： https://developer.apple.com/documentation/SwiftUI/Scoping-a-search-operation
抓取时间： 2025-12-02T17:31:42Z
---

# 搜索操作的范围

**Article**

将搜索空间分为几大类。

## 概览

如果要搜索的数据属于几个类别，您可以定义不同的范围，帮助用户缩小搜索范围。定义范围后，SwiftUI 会显示一个选择器，供用户选择其中之一。然后，您就可以使用当前范围选择作为搜索操作的输入之一。

###定义可能的范围

首先创建一个符合[doc://com.apple.documentation/documentation/Swift/Hashable] 协议的类型来表示可能的作用域。例如，您可以使用枚举将产品搜索范围限定为水果或蔬菜：

```swift
enum ProductScope {
    case fruit
    case vegetable
}
```

然后创建一个属性来存储当前范围，可以是视图中的状态变量，也可以是模型中的发布属性：

```swift
@Published var scope: ProductScope = .fruit
```

### 应用作用域

要使用作用域信息，请将当前作用域绑定到 [searchScopes(_:scopes:)](View/searchScopes___scopes.zh-Hans.md) 修改器。您还可以指出一组与不同作用域相对应的视图。与[searchSuggestions(_:)](View/searchSuggestions.zh-Hans.md)修饰符一样，作用域修饰符的操作对象是更接近被修改视图的可搜索修饰符，因此它需要跟随在可搜索修饰符之后：

```swift
ProductList(departmentId: departmentId, productId: $productId)
    .searchable(text: $model.searchText, tokens: $model.tokens) { token in
        switch token {
        case .apple: Text("Apple")
        case .pear: Text("Pear")
        case .banana: Text("Banana")
        }
    }
    .searchScopes($model.scope) {
        Text("Fruit").tag(ProductScope.fruit)
        Text("Vegetable").tag(ProductScope.vegetable)
    }
```

SwiftUI 使用绑定和视图为搜索字段添加[Picker](Picker.zh-Hans.md)。默认情况下，在 macOS 中，当搜索处于活动状态时，拾取器会出现在搜索字段的下方；在 iOS 中，当有人开始在搜索字段中输入文本时，拾取器会出现在搜索字段的下方：



您可以使用[searchScopes(_:activation:_:)](View/searchScopes___activation.zh-Hans.md)修饰符，并提供其中一个[SearchScopeActivation](SearchScopeActivation.zh-Hans.md)值，如[onTextEntry](SearchScopeActivation/onTextEntry.zh-Hans.md)或[onSearchPresentation](SearchScopeActivation/onSearchPresentation.zh-Hans.md)，来更改选取器的显示时间。

为确保拾取器正确运行，请将作用域绑定的类型与每个视图标记的类型相匹配。在上例中，`scope` 输入和每个视图的标记都是`ProductScope` 类型。

### 在搜索中使用范围

如果您提供`scope` 属性的当前值，请修改您的搜索，以便将其与查询中的文本和标记一起考虑在内。例如，您可以将范围作为您为核心数据获取请求定义的谓词的一个元素。有关进行搜索的更多信息，请参阅 [Performing-a-search-operation](Performing-a-search-operation.zh-Hans.md)。

## 限制搜索范围

- **searchScopes(_:scopes:)**：配置此视图的搜索范围。
- **searchScopes(_:activation:_:)**：使用指定的激活策略为该视图配置搜索范围。
- **SearchScopeActivation**：可搜索修改器显示或隐藏搜索范围的方式。


---
source: https://developer.apple.com/documentation/SwiftUI/Scoping-a-search-operation
crawled: 2025-12-02T17:31:42Z
---

# Scoping a search operation

**Article**

Divide the search space into a few broad categories.

## Overview

If the data you want to search falls into a few categories, you can define different scopes to help people narrow their search. When you define a scope, SwiftUI presents a picker that people can use to choose one of them. You then use the current scope selection as one of the inputs to the search operation.

### Define the possible scopes

Start by creating a type that conforms to the [doc://com.apple.documentation/documentation/Swift/Hashable] protocol to represent the possible scopes. For example, you can use an enumeration to scope a product search to just fruits or just vegetables:

```swift
enum ProductScope {
    case fruit
    case vegetable
}
```

Then create a property to store the current scope, either as a state variable in a view, or a published property in your model:

```swift
@Published var scope: ProductScope = .fruit
```

### Apply the scope

To use the scope information, bind the current scope to the [searchScopes(_:scopes:)](View/searchScopes___scopes.zh-Hans.md) modifier. You also indicate a set of views that correspond to the different scopes. Like the [searchSuggestions(_:)](View/searchSuggestions.zh-Hans.md) modifier, the scopes modifier operates on the searchable modifier that’s closer to the modified view, so it needs to follow the searchable modifier:

```swift
ProductList(departmentId: departmentId, productId: $productId)
    .searchable(text: $model.searchText, tokens: $model.tokens) { token in
        switch token {
        case .apple: Text("Apple")
        case .pear: Text("Pear")
        case .banana: Text("Banana")
        }
    }
    .searchScopes($model.scope) {
        Text("Fruit").tag(ProductScope.fruit)
        Text("Vegetable").tag(ProductScope.vegetable)
    }
```

SwiftUI uses the binding and views to add a [Picker](Picker.zh-Hans.md) to the search field. By default, the picker appears below the search field in macOS when search is active, or in iOS when someone starts entering text into the search field:



You can change when the picker appears by using the [searchScopes(_:activation:_:)](View/searchScopes___activation.zh-Hans.md) modifier instead, and supplying one of the [SearchScopeActivation](SearchScopeActivation.zh-Hans.md) values, like [onTextEntry](SearchScopeActivation/onTextEntry.zh-Hans.md) or [onSearchPresentation](SearchScopeActivation/onSearchPresentation.zh-Hans.md).

To ensure that the picker operates correctly, match the type of the scope binding with the type of each view’s tag. In the above example, both the `scope` input and the tags for each view have the type `ProductScope`.

### Use the scope in your search

Modify your search to account for the current value of the `scope` property, if you offer it, along with the text and tokens in the query. For example, you might include the scope as one element of a predicate that you define for a Core Data fetch request. For more information about conducting a search, see [Performing-a-search-operation](Performing-a-search-operation.zh-Hans.md).

## Limiting search scope

- **searchScopes(_:scopes:)**: Configures the search scopes for this view.
- **searchScopes(_:activation:_:)**: Configures the search scopes for this view with the specified activation strategy.
- **SearchScopeActivation**: The ways that searchable modifiers can show or hide search scopes.

