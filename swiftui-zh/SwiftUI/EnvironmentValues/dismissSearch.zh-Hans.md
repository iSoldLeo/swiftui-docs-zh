---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/dismissSearch
抓取时间： 2025-12-02T17:31:47Z
---

# dismissSearch

**实例属性**

结束当前搜索交互的操作。

## 声明

```swift
var dismissSearch: DismissSearchAction { get }
```

## 讨论

使用此环境值可获取当前 [DismissSearchAction](../DismissSearchAction.zh-Hans.md) 的 [Environment](../Environment.zh-Hans.md) 实例。然后调用该实例来解除当前的搜索交互。您直接调用该实例是因为它定义了一个 [callAsFunction()](../DismissSearchAction/callAsFunction.zh-Hans.md) 方法，当您调用该实例时，Swift 会调用该方法。

当您取消搜索时，SwiftUI.NET 会调用该方法：

- 将 [isSearching](isSearching.zh-Hans.md) 设置为 `false`。
- 清除搜索栏中的任何文本。
- 从搜索栏移除焦点。



使用此操作可根据其他用户交互解除搜索操作。例如，考虑一个带有[Button](../Button.zh-Hans.md)的可搜索视图，该视图会显示集合中第一个匹配项的更多信息：

```swift
struct ContentView: View {
    @State private var searchText = ""

    var body: some View {
        NavigationStack {
            SearchedView(searchText: searchText)
                .searchable(text: $searchText)
        }
    }
}

private struct SearchedView: View {
    let searchText: String

    let items = ["a", "b", "c"]
    var filteredItems: [String] { items.filter { $0 == searchText.lowercased() } }

    @State private var isPresented = false
    @Environment(\.dismissSearch) private var dismissSearch

    var body: some View {
        if let item = filteredItems.first {
            Button("Details about \(item)") {
                isPresented = true
            }
            .sheet(isPresented: $isPresented) {
                NavigationStack {
                    DetailView(item: item, dismissSearch: dismissSearch)
                }
            }
        }
    }
}
```

该按钮只有在用户输入搜索文本并产生匹配结果后才会显示。当用户点击该按钮时，SwiftUI 会显示一个工作表，提供有关项目的更多信息，包括一个添加按钮，用于将项目添加到存储的项目列表中：

```swift
private struct DetailView: View {
    var item: String
    var dismissSearch: DismissSearchAction

    @Environment(\.dismiss) private var dismiss

    var body: some View {
        Text("Information about \(item).")
            .toolbar {
                Button("Add") {
                    // Store the item here...

                    dismiss()
                    dismissSearch()
                }
            }
    }
}
```

用户可以通过向下拖动来取消工作表，从而有效地取消操作，使正在进行的搜索交互保持完整。或者，用户可以点击添加按钮来存储项目。由于使用您应用程序的人此时可能已经完成了详细视图和搜索交互，因此按钮的关闭也使用[dismiss](dismiss.zh-Hans.md) 属性来取消工作表，并使用[dismissSearch](dismissSearch.zh-Hans.md) 属性来重置搜索字段。



## 检测、激活和取消搜索

- 管理搜索界面的激活**：以编程方式检测和取消搜索栏。
- **isSearching**：布尔值，表示用户何时正在搜索。
- **DismissSearchAction**：可以结束搜索交互的操作。
- **searchable(text:isPresented:placement:prompt:)**：将此视图标记为可搜索视图，并通过程序显示搜索字段。
- **searchable(text:tokens:isPresented:placement:prompt:token:)**：将此视图标记为可通过文本和标记以及程序化显示进行搜索。
- **searchable(text:editableTokens:isPresented:placement:prompt:token:)**：将此视图标记为可搜索视图，并配置显示搜索字段。
- **searchable(text:tokens:suggestedTokens:isPresented:placement:prompt:token:)**：将此视图标记为可通过文本、标记和建议以及编程显示进行搜索。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/dismissSearch
crawled: 2025-12-02T17:31:47Z
---

# dismissSearch

**Instance Property**

An action that ends the current search interaction.

## Declaration

```swift
var dismissSearch: DismissSearchAction { get }
```

## Discussion

Use this environment value to get the [DismissSearchAction](../DismissSearchAction.zh-Hans.md) instance for the current [Environment](../Environment.zh-Hans.md). Then call the instance to dismiss the current search interaction. You call the instance directly because it defines a [callAsFunction()](../DismissSearchAction/callAsFunction.zh-Hans.md) method that Swift calls when you call the instance.

When you dismiss search, SwiftUI:

- Sets [isSearching](isSearching.zh-Hans.md) to `false`.
- Clears any text from the search field.
- Removes focus from the search field.



Use this action to dismiss a search operation based on another user interaction. For example, consider a searchable view with a [Button](../Button.zh-Hans.md) that presents more information about the first matching item from a collection:

```swift
struct ContentView: View {
    @State private var searchText = ""

    var body: some View {
        NavigationStack {
            SearchedView(searchText: searchText)
                .searchable(text: $searchText)
        }
    }
}

private struct SearchedView: View {
    let searchText: String

    let items = ["a", "b", "c"]
    var filteredItems: [String] { items.filter { $0 == searchText.lowercased() } }

    @State private var isPresented = false
    @Environment(\.dismissSearch) private var dismissSearch

    var body: some View {
        if let item = filteredItems.first {
            Button("Details about \(item)") {
                isPresented = true
            }
            .sheet(isPresented: $isPresented) {
                NavigationStack {
                    DetailView(item: item, dismissSearch: dismissSearch)
                }
            }
        }
    }
}
```

The button becomes visible only after the user enters search text that produces a match. When the user taps the button, SwiftUI shows a sheet that provides more information about the item, including an Add button for adding the item to a stored list of items:

```swift
private struct DetailView: View {
    var item: String
    var dismissSearch: DismissSearchAction

    @Environment(\.dismiss) private var dismiss

    var body: some View {
        Text("Information about \(item).")
            .toolbar {
                Button("Add") {
                    // Store the item here...

                    dismiss()
                    dismissSearch()
                }
            }
    }
}
```

People can dismiss the sheet by dragging it down, effectively canceling the operation, leaving the in-progress search interaction intact. Alternatively, people can tap the Add button to store the item. Because the person using your app is likely to be done with both the detail view and the search interaction at this point, the button’s closure also uses the [dismiss](dismiss.zh-Hans.md) property to dismiss the sheet, and the [dismissSearch](dismissSearch.zh-Hans.md) property to reset the search field.



## Detecting, activating, and dismissing search

- **Managing search interface activation**: Programmatically detect and dismiss a search field.
- **isSearching**: A Boolean value that indicates when the user is searching.
- **DismissSearchAction**: An action that can end a search interaction.
- **searchable(text:isPresented:placement:prompt:)**: Marks this view as searchable with programmatic presentation of the search field.
- **searchable(text:tokens:isPresented:placement:prompt:token:)**: Marks this view as searchable with text and tokens, as well as programmatic presentation.
- **searchable(text:editableTokens:isPresented:placement:prompt:token:)**: Marks this view as searchable, which configures the display of a search field.
- **searchable(text:tokens:suggestedTokens:isPresented:placement:prompt:token:)**: Marks this view as searchable with text, tokens, and suggestions, as well as programmatic presentation.

