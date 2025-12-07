--- 来源：https://developer.apple.com/documentation/SwiftUI/View/searchable(text:tokens:suggestedTokens:isPresented:placement:prompt:token:)

抓取时间：2025-12-02T17:31:51Z

---

# searchable(text:tokens:suggestedTokens:isPresented:placement:prompt:token:)

**实例方法**

将此视图标记为可搜索，支持文本、词元和搜索建议，以及程序化呈现。

## 声明

```swift
nonisolated func searchable<C, T, S>(text: Binding<String>, tokens: Binding<C>, suggestedTokens: Binding<C>, isPresented: Binding<Bool>, placement: SearchFieldPlacement = .automatic, prompt: S, @ViewBuilder token: @escaping (C.Element) -> T) -> some View where C : MutableCollection, C : RandomAccessCollection, C : RangeReplaceableCollection, T : View, S : StringProtocol, C.Element : Identifiable

```

## 参数

- **text**：要在搜索字段中显示和编辑的文本。

- **tokens**：要在搜索字段中显示和编辑的词元集合。

- **suggestedTokens**：用于显示建议的标记集合。

- **placement**：搜索字段在包含视图层次结构中的首选位置。

- **prompt**：表示搜索字段提示的字符串，用于指导用户搜索内容。

- **token**：视图构建器，可根据标记中的元素创建视图。

## 讨论

有关使用可搜索修饰符的更多信息，请参阅 [Adding-a-search-interface-to-your-app](../Adding-a-search-interface-to-your-app.zh-Hans.md)。有关以编程方式呈现搜索字段的信息，请参阅 [Managing-search-interface-activation](../Managing-search-interface-activation.zh-Hans.md)。

## 检测、激活和关闭搜索

- **管理搜索界面激活**：以编程方式检测和关闭搜索字段。

- **isSearching**：一个布尔值，指示用户何时处于搜索状态。

- **dismissSearch**：结束当前搜索交互的操作。

- **DismissSearchAction**：可以结束搜索交互的操作。

- **searchable(text:isPresented:placement:prompt:)**：将此视图标记为可搜索，并以编程方式显示搜索字段。

- **searchable(text:tokens:isPresented:placement:prompt:token:)**：将此视图标记为可搜索，支持文本和词元搜索，以及以编程方式显示搜索字段。

- **searchable(text:editableTokens:isPresented:placement:prompt:token:)**：将此视图标记为可搜索，并配置搜索字段的显示。


---
source: https://developer.apple.com/documentation/SwiftUI/View/searchable(text:tokens:suggestedTokens:isPresented:placement:prompt:token:)
crawled: 2025-12-02T17:31:51Z
---

# searchable(text:tokens:suggestedTokens:isPresented:placement:prompt:token:)

**Instance Method**

Marks this view as searchable with text, tokens, and suggestions, as well as programmatic presentation.

## Declaration

```swift
nonisolated func searchable<C, T, S>(text: Binding<String>, tokens: Binding<C>, suggestedTokens: Binding<C>, isPresented: Binding<Bool>, placement: SearchFieldPlacement = .automatic, prompt: S, @ViewBuilder token: @escaping (C.Element) -> T) -> some View where C : MutableCollection, C : RandomAccessCollection, C : RangeReplaceableCollection, T : View, S : StringProtocol, C.Element : Identifiable

```

## Parameters

- **text**: The text to display and edit in the search field.
- **tokens**: A collection of tokens to display and edit in the search field.
- **suggestedTokens**: A collection of tokens to display as suggestions.
- **placement**: The preferred placement of the search field within the containing view hierarchy.
- **prompt**: A string representing the prompt of the search field which provides users with guidance on what to search for.
- **token**: A view builder that creates a view given an element in tokens.

## Discussion

For more information about using searchable modifiers, see [Adding-a-search-interface-to-your-app](../Adding-a-search-interface-to-your-app.zh-Hans.md). For information about presenting a search field programmatically, see [Managing-search-interface-activation](../Managing-search-interface-activation.zh-Hans.md).

## Detecting, activating, and dismissing search

- **Managing search interface activation**: Programmatically detect and dismiss a search field.
- **isSearching**: A Boolean value that indicates when the user is searching.
- **dismissSearch**: An action that ends the current search interaction.
- **DismissSearchAction**: An action that can end a search interaction.
- **searchable(text:isPresented:placement:prompt:)**: Marks this view as searchable with programmatic presentation of the search field.
- **searchable(text:tokens:isPresented:placement:prompt:token:)**: Marks this view as searchable with text and tokens, as well as programmatic presentation.
- **searchable(text:editableTokens:isPresented:placement:prompt:token:)**: Marks this view as searchable, which configures the display of a search field.

