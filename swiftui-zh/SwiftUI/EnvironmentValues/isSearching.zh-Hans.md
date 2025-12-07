---
来源：https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/isSearching
抓取时间： 2025-12-02T17:31:46Z
---

# isSearching

**实例属性**

布尔值，表示用户正在搜索。

## 声明

```swift
var isSearching: Bool { get }
```

## 讨论

通过使用[Environment](../Environment.zh-Hans.md) 属性包装器创建属性，您可以像读取其他[EnvironmentValues](../EnvironmentValues.zh-Hans.md) 属性一样读取该值：

```swift
@Environment(\.isSearching) private var isSearching
```

当用户与一个由[searchable(text:placement:prompt:)](../View/searchable_text_placement_prompt.zh-Hans.md)等可搜索修饰符生成的搜索字段交互时，获取该值：

```swift
struct SearchingExample: View {
    @State private var searchText = ""

    var body: some View {
        NavigationStack {
            SearchedView()
                .searchable(text: $searchText)
        }
    }
}

struct SearchedView: View {
    @Environment(\.isSearching) private var isSearching

    var body: some View {
        Text(isSearching ? "Searching!" : "Not searching.")
    }
}
```

当用户第一次点击或单击搜索字段时，`isSearching` 属性会变成 `true`。当用户取消搜索操作时，属性会变成 `false`。要通过编程将该值设置为 `false` 并取消搜索操作，请使用 [dismissSearch](dismissSearch.zh-Hans.md)。



## 检测、激活和取消搜索

- 管理搜索界面的激活**：以编程方式检测和取消搜索栏。
- **dismissSearch**：结束当前搜索交互的操作。
- **DismissSearchAction**：可以结束搜索交互的操作。
- **searchable(text:isPresented:placement:prompt:)**：将此视图标记为可搜索视图，并以编程方式显示搜索字段。
- **searchable(text:tokens:isPresented:placement:prompt:token:)**：将此视图标记为可通过文本和标记以及程序化显示进行搜索。
- **searchable(text:editableTokens:isPresented:placement:prompt:token:)**：将此视图标记为可搜索视图，并配置显示搜索字段。
- **searchable(text:tokens:suggestedTokens:isPresented:placement:prompt:token:)**：将此视图标记为可通过文本、标记和建议以及编程显示进行搜索。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/isSearching
crawled: 2025-12-02T17:31:46Z
---

# isSearching

**Instance Property**

A Boolean value that indicates when the user is searching.

## Declaration

```swift
var isSearching: Bool { get }
```

## Discussion

You can read this value like any of the other [EnvironmentValues](../EnvironmentValues.zh-Hans.md), by creating a property with the [Environment](../Environment.zh-Hans.md) property wrapper:

```swift
@Environment(\.isSearching) private var isSearching
```

Get the value to find out when the user interacts with a search field that’s produced by one of the searchable modifiers, like [searchable(text:placement:prompt:)](../View/searchable_text_placement_prompt.zh-Hans.md):

```swift
struct SearchingExample: View {
    @State private var searchText = ""

    var body: some View {
        NavigationStack {
            SearchedView()
                .searchable(text: $searchText)
        }
    }
}

struct SearchedView: View {
    @Environment(\.isSearching) private var isSearching

    var body: some View {
        Text(isSearching ? "Searching!" : "Not searching.")
    }
}
```

When the user first taps or clicks in a search field, the `isSearching` property becomes `true`. When the user cancels the search operation, the property becomes `false`. To programmatically set the value to `false` and dismiss the search operation, use [dismissSearch](dismissSearch.zh-Hans.md).



## Detecting, activating, and dismissing search

- **Managing search interface activation**: Programmatically detect and dismiss a search field.
- **dismissSearch**: An action that ends the current search interaction.
- **DismissSearchAction**: An action that can end a search interaction.
- **searchable(text:isPresented:placement:prompt:)**: Marks this view as searchable with programmatic presentation of the search field.
- **searchable(text:tokens:isPresented:placement:prompt:token:)**: Marks this view as searchable with text and tokens, as well as programmatic presentation.
- **searchable(text:editableTokens:isPresented:placement:prompt:token:)**: Marks this view as searchable, which configures the display of a search field.
- **searchable(text:tokens:suggestedTokens:isPresented:placement:prompt:token:)**: Marks this view as searchable with text, tokens, and suggestions, as well as programmatic presentation.

