--- 来源：https://developer.apple.com/documentation/SwiftUI/Adding-a-search-interface-to-your-app

抓取时间：2025-12-02T17:31:31Z

---

# 为您的应用添加搜索界面

**Article**

提供一个界面，供用户在您的应用中搜索内容。

## 概述

通过将可搜索视图修饰符（例如 [searchable(text:placement:prompt:)](View/searchable_text_placement_prompt.zh-Hans.md)）应用于 [NavigationSplitView](NavigationSplitView.zh-Hans.md) 或 [NavigationStack](NavigationStack.zh-Hans.md)，或者应用于这些视图内部的某个视图，即可为您的应用添加搜索界面。之后，工具栏中将显示一个搜索框。搜索框的具体位置和外观取决于平台、修饰符在代码中的位置及其配置。

创建搜索字段的可搜索修饰符接受一个 [Binding](Binding.zh-Hans.md) 参数，该参数指向一个表示搜索字段文本的字符串。您需要提供存储该字符串的空间，以及（可选地）用于执行搜索的离散搜索标记数组。要了解如何管理搜索字段的数据，请参阅 [Performing-a-search-operation](Performing-a-search-operation.zh-Hans.md)。

### 自动放置搜索字段

您可以通过将 [searchable(text:placement:prompt:)](View/searchable_text_placement_prompt.zh-Hans.md) 修饰符添加到导航元素（例如导航拆分视图）来自动放置搜索字段：

```swift
struct ContentView: View {
    @State private var departmentId: Department.ID?
    @State private var productId: Product.ID?
    @State private var searchText: String = ""

    var body: some View {
        NavigationSplitView {
            DepartmentList(departmentId: $departmentId)
        } content: {
            ProductList(departmentId: departmentId, productId: $productId)
        } detail: {
            ProductDetails(productId: productId)
        }
        .searchable(text: $searchText) // Adds a search field.
    }
}
```

通过此配置，搜索字段将显示在 macOS 工具栏的尾部。在 iOS 和 iPadOS 中，搜索字段分别显示在双列或三列导航视图的第一列或第二列中。上面的三列示例将搜索字段放置在 iPad 上中间列的顶部。

### 通过结构控制位置

要在 iOS 和 iPadOS 中向特定列添加搜索字段，请将可搜索修饰符添加到该列中的视图。例如，要指示搜索范围涵盖上例中的部门，您可以将搜索字段放置在第一列中，方法是将修饰符添加到该列的 `DepartmentList` 视图，而不是添加到导航拆分视图：

```swift
NavigationSplitView {
    DepartmentList(departmentId: $departmentId)
        .searchable(text: $searchText)
} content: {
    ProductList(departmentId: departmentId, productId: $productId)
} detail: {
    ProductDetails(productId: productId)
}
```

### 通过编程控制位置

您也可以使用 `placement` 输入参数来建议搜索界面的 [SearchFieldPlacement](SearchFieldPlacement.zh-Hans.md) 值。例如，在 macOS 中，您可以使用 [sidebar](SearchFieldPlacement/sidebar.zh-Hans.md) 位置实现与上一个示例相同的效果：

```swift
NavigationSplitView {
    DepartmentList(departmentId: $departmentId)
} content: {
    ProductList(departmentId: departmentId, productId: $productId)
} detail: {
    ProductDetails(productId: productId)
}
.searchable(text: $searchText, placement: .sidebar)
```

如果 SwiftUI 无法满足位置请求，例如当您请求在未应用于导航拆分视图的可搜索修饰符中放置侧边栏时，SwiftUI 会依赖其自动位置规则。

### 设置搜索字段的提示

默认情况下，搜索字段包含“搜索”作为占位符文本，以提示用户如何使用该字段。您可以通过为可搜索修饰符的 `prompt` 输入参数设置字符串、[Text](Text.zh-Hans.md) 视图或 [LocalizedStringKey](LocalizedStringKey.zh-Hans.md) 来自定义提示。例如，您可以使用以下方式明确“部门”列中的搜索字段会搜索所有部门以及每个部门下的产品：

```swift
DepartmentList(departmentId: $departmentId)
    .searchable(text: $searchText, prompt: "Departments and products")
```

## 搜索应用程序的数据模型

- **执行搜索操作**：根据您存储的搜索文本和可选标记更新搜索结果。

- **searchable(text:placement:prompt:)**：将此视图标记为可搜索，从而配置搜索字段的显示。

- **searchable(text:tokens:placement:prompt:token:)**：使用此文本和标记将此视图标记为可搜索。

- **searchable(text:editableTokens:placement:prompt:token:)**：将此视图标记为可搜索，从而配置搜索字段的显示。

- **SearchFieldPlacement**：在视图层次结构中放置搜索字段。


---
source: https://developer.apple.com/documentation/SwiftUI/Adding-a-search-interface-to-your-app
crawled: 2025-12-02T17:31:31Z
---

# Adding a search interface to your app

**Article**

Present an interface that people can use to search for content in your app.

## Overview

Add a search interface to your app by applying one of the searchable view modifiers — like [searchable(text:placement:prompt:)](View/searchable_text_placement_prompt.zh-Hans.md) — to a [NavigationSplitView](NavigationSplitView.zh-Hans.md) or [NavigationStack](NavigationStack.zh-Hans.md), or to a view inside one of these. A search field then appears in the toolbar. The precise placement and appearance of the search field depends on the platform, where you put the modifier in code, and its configuration.



The searchable modifier that creates the field takes a [Binding](Binding.zh-Hans.md) to a string that represents the search field’s text. You provide the storage for the string — and optionally for an array of discrete search tokens — that you use to conduct the search. To learn about managing the search field’s data, see [Performing-a-search-operation](Performing-a-search-operation.zh-Hans.md).

### Place the search field automatically

You can automatically place the search field by adding the [searchable(text:placement:prompt:)](View/searchable_text_placement_prompt.zh-Hans.md) modifier to a navigation element like a navigation split view:

```swift
struct ContentView: View {
    @State private var departmentId: Department.ID?
    @State private var productId: Product.ID?
    @State private var searchText: String = ""

    var body: some View {
        NavigationSplitView {
            DepartmentList(departmentId: $departmentId)
        } content: {
            ProductList(departmentId: departmentId, productId: $productId)
        } detail: {
            ProductDetails(productId: productId)
        }
        .searchable(text: $searchText) // Adds a search field.
    }
}
```

With this configuration, the search field appears on the trailing edge of the toolbar in macOS. In iOS and iPadOS, the first or second column displays the search field in a double or triple column navigation view, respectively. The above three-column example puts the search field at the top of the middle column on iPad.



### Control the placement structurally

To add a search field to a specific column in iOS and iPadOS, add the searchable modifier to a view in that column. For example, to indicate that the search covers departments in the previous example, you could place the search field in the first column by adding the modifier to that column’s `DepartmentList` view instead of to the navigation split view:

```swift
NavigationSplitView {
    DepartmentList(departmentId: $departmentId)
        .searchable(text: $searchText)
} content: {
    ProductList(departmentId: departmentId, productId: $productId)
} detail: {
    ProductDetails(productId: productId)
}
```



### Control the placement programmatically

You can alternatively use the `placement` input parameter to suggest a [SearchFieldPlacement](SearchFieldPlacement.zh-Hans.md) value for the search interface. For example, you can achieve the same results as the previous example in macOS using the [sidebar](SearchFieldPlacement/sidebar.zh-Hans.md) placement:

```swift
NavigationSplitView {
    DepartmentList(departmentId: $departmentId)
} content: {
    ProductList(departmentId: departmentId, productId: $productId)
} detail: {
    ProductDetails(productId: productId)
}
.searchable(text: $searchText, placement: .sidebar)
```



If SwiftUI can’t satisfy the placement request, like when you ask for sidebar placement in a searchable modifier that isn’t applied to a navigation split view, SwiftUI relies instead on its automatic placement rules.

### Set a prompt for the search field

By default, the search field contains Search as the placeholder text, to prompt people on how to use the field. You can customize the prompt by setting either a string, a [Text](Text.zh-Hans.md) view, or a [LocalizedStringKey](LocalizedStringKey.zh-Hans.md) for the searchable modifier’s `prompt` input parameter. For example, you might use this to clarify that the search field in the Department column searches among both departments and the products in each department:

```swift
DepartmentList(departmentId: $departmentId)
    .searchable(text: $searchText, prompt: "Departments and products")
```



## Searching your app’s data model

- **Performing a search operation**: Update search results based on search text and optional tokens that you store.
- **searchable(text:placement:prompt:)**: Marks this view as searchable, which configures the display of a search field.
- **searchable(text:tokens:placement:prompt:token:)**: Marks this view as searchable with text and tokens.
- **searchable(text:editableTokens:placement:prompt:token:)**: Marks this view as searchable, which configures the display of a search field.
- **SearchFieldPlacement**: The placement of a search field in a view hierarchy.

