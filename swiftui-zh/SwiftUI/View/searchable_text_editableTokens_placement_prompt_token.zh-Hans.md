--- 来源：https://developer.apple.com/documentation/SwiftUI/View/searchable(text:editableTokens:placement:prompt:token:)

抓取时间：2025-11-30T21:16:40Z

---

# searchable(text:editableTokens:placement:prompt:token:)

**实例方法**

将此视图标记为可搜索，从而配置搜索字段的显示。

## 声明

```swift
nonisolated func searchable<C>(text: Binding<String>, editableTokens: Binding<C>, placement: SearchFieldPlacement = .automatic, prompt: LocalizedStringKey, @ViewBuilder token: @escaping (Binding<C.Element>) -> some View) -> some View where C : RandomAccessCollection, C : RangeReplaceableCollection, C.Element : Identifiable

```

## 参数

- **text**：要在搜索字段中显示和编辑的文本。

- **editableTokens**：要在搜索字段中显示和编辑的标记集合。

- **placement**：搜索字段在包含视图层次结构中的首选位置。

- **prompt**：用于搜索字段本地化提示的键，为用户提供搜索内容的指导。

- **token**：视图构建器，可根据令牌中的元素创建视图。

## 讨论

有关使用可搜索修饰符的更多信息，请参阅 [Adding-a-search-interface-to-your-app](../Adding-a-search-interface-to-your-app.zh-Hans.md)。

## 搜索应用的数据模型

- **向应用添加搜索界面**：提供一个界面，供用户搜索应用内的内容。

- **执行搜索操作**：根据搜索文本和您存储的可选令牌更新搜索结果。

- **searchable(text:placement:prompt:)**：将此视图标记为可搜索，从而配置搜索字段的显示。

- **searchable(text:tokens:placement:prompt:token:)**：使用此文本和令牌将此视图标记为可搜索。

- **SearchFieldPlacement**：搜索字段在视图层级结构中的位置。


---
source: https://developer.apple.com/documentation/SwiftUI/View/searchable(text:editableTokens:placement:prompt:token:)
crawled: 2025-11-30T21:16:40Z
---

# searchable(text:editableTokens:placement:prompt:token:)

**Instance Method**

Marks this view as searchable, which configures the display of a search field.

## Declaration

```swift
nonisolated func searchable<C>(text: Binding<String>, editableTokens: Binding<C>, placement: SearchFieldPlacement = .automatic, prompt: LocalizedStringKey, @ViewBuilder token: @escaping (Binding<C.Element>) -> some View) -> some View where C : RandomAccessCollection, C : RangeReplaceableCollection, C.Element : Identifiable

```

## Parameters

- **text**: The text to display and edit in the search field.
- **editableTokens**: A collection of tokens to display and edit in the search field.
- **placement**: The preferred placement of the search field within the containing view hierarchy.
- **prompt**: The key for the localized prompt of the search field which provides users with guidance on what to search for.
- **token**: A view builder that creates a view given an element in tokens.

## Discussion

For more information about using searchable modifiers, see [Adding-a-search-interface-to-your-app](../Adding-a-search-interface-to-your-app.zh-Hans.md).

## Searching your app’s data model

- **Adding a search interface to your app**: Present an interface that people can use to search for content in your app.
- **Performing a search operation**: Update search results based on search text and optional tokens that you store.
- **searchable(text:placement:prompt:)**: Marks this view as searchable, which configures the display of a search field.
- **searchable(text:tokens:placement:prompt:token:)**: Marks this view as searchable with text and tokens.
- **SearchFieldPlacement**: The placement of a search field in a view hierarchy.

