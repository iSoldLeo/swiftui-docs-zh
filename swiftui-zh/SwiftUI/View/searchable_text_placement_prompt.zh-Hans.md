--- 来源：https://developer.apple.com/documentation/SwiftUI/View/searchable(text:placement:prompt:)

抓取时间：2025-11-30T21:16:38Z

---

# searchable(text:placement:prompt:)

**实例方法**

将此视图标记为可搜索，从而配置搜索字段的显示。

## 声明

```swift
nonisolated func searchable(text: Binding<String>, placement: SearchFieldPlacement = .automatic, prompt: LocalizedStringKey) -> some View

```

## 参数

- **text**：要在搜索字段中显示和编辑的文本。

- **placement**：搜索字段在包含视图层次结构中的首选位置。

- **prompt**：搜索字段本地化提示的键，用于指导用户搜索内容。

## 讨论

有关使用可搜索修饰符的更多信息，请参阅 [Adding-a-search-interface-to-your-app](../Adding-a-search-interface-to-your-app.zh-Hans.md)。

## 搜索应用的数据模型

- **向应用添加搜索界面**：提供一个界面，供用户搜索应用内的内容。

- **执行搜索操作**：根据搜索文本和您存储的可选标记更新搜索结果。

- **searchable(text:tokens:placement:prompt:token:)**：将此视图标记为可使用文本和标记进行搜索。

- **searchable(text:editableTokens:placement:prompt:token:)**：将此视图标记为可搜索，这将配置搜索字段的显示。

- **SearchFieldPlacement**：在视图层次结构中放置搜索字段。


---
source: https://developer.apple.com/documentation/SwiftUI/View/searchable(text:placement:prompt:)
crawled: 2025-11-30T21:16:38Z
---

# searchable(text:placement:prompt:)

**Instance Method**

Marks this view as searchable, which configures the display of a search field.

## Declaration

```swift
nonisolated func searchable(text: Binding<String>, placement: SearchFieldPlacement = .automatic, prompt: LocalizedStringKey) -> some View

```

## Parameters

- **text**: The text to display and edit in the search field.
- **placement**: The preferred placement of the search field within the containing view hierarchy.
- **prompt**: The key for the localized prompt of the search field which provides users with guidance on what to search for.

## Discussion

For more information about using searchable modifiers, see [Adding-a-search-interface-to-your-app](../Adding-a-search-interface-to-your-app.zh-Hans.md).

## Searching your app’s data model

- **Adding a search interface to your app**: Present an interface that people can use to search for content in your app.
- **Performing a search operation**: Update search results based on search text and optional tokens that you store.
- **searchable(text:tokens:placement:prompt:token:)**: Marks this view as searchable with text and tokens.
- **searchable(text:editableTokens:placement:prompt:token:)**: Marks this view as searchable, which configures the display of a search field.
- **SearchFieldPlacement**: The placement of a search field in a view hierarchy.

