--- 来源：https://developer.apple.com/documentation/SwiftUI/Managing-search-interface-activation
抓取时间：2025-12-02T17:31:45Z

---

# 管理搜索界面激活

**Article**

以编程方式检测并关闭搜索框。

## 概述

用户通过点击或轻触应用内的搜索框来激活它，之后即可输入搜索词。在许多情况下，您的应用只需响应搜索文本值的相应变化即可，界面会通过您提供的绑定来更新这些值，如 [Performing-a-search-operation](Performing-a-search-operation.zh-Hans.md) 中所述。

但是，SwiftUI 也提供了一些控件，使您能够以编程方式管理搜索界面。具体来说，您可以：

- 使用您提供的绑定（指向 searchable 修饰符）来激活或停用界面。

- 通过读取环境变量值来检测界面是否处于激活状态。

- 通过调用存储在环境中的操作来关闭界面。

- 等待搜索提交事件后再开始搜索。

### 通过绑定控制激活

您可以通过为可搜索修饰符的 `isPresented` 参数提供布尔值 [Binding](Binding.zh-Hans.md) 来以编程方式控制搜索界面的激活。例如，要显示一个工作表，并在显示时搜索界面已激活，请创建一个初始值为 true 的绑定：

```swift
struct SheetView: View {
    @State private var isPresented = true
    @State private var text = ""
  
    var body: some View {
        NavigationStack {
            SheetContent()
                .searchable(text: $text, isPresented: $isPresented)
        }
    }
}   
```

在 iOS 和 macOS 上，SwiftUI 会在显示搜索时聚焦搜索字段，并在关闭搜索时取消聚焦搜索字段。搜索字段也可能在搜索界面仍然显示的情况下失去焦点。例如，如果您的搜索界面包含一个文本字段列表，用户可能会将焦点移动到其中一个文本字段，而不会关闭界面。

### 检测搜索激活状态

如果您需要了解搜索界面何时处于激活状态，可以使用 [Environment](Environment.zh-Hans.md) 属性包装器查询环境的 [isSearching](EnvironmentValues/isSearching.zh-Hans.md) 属性。以下示例展示了一个视图，该视图会根据属性状态更新其显示的文本：

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
        Text(isSearching ? "Searching" : "Not searching")
    }
}
```

当用户首次点击或单击搜索字段时，`isSearching` 属性会变为 `true`。当用户取消搜索操作时，该属性会变为 `false`。如果您以编程方式关闭界面（如下一节所述），该属性也会变为 `false`。

务必从被 [searchable(text:placement:prompt:)](View/searchable_text_placement_prompt.zh-Hans.md) 视图修饰符（例如上例中的 `SearchedView`）直接或间接包裹的视图内部读取属性。如果从该上下文之外读取属性值（例如将其放在 `SearchingExample` 视图中），则无法检测到属性值的任何变化。

### 关闭搜索界面

您可以使用环境的 [dismissSearch](EnvironmentValues/dismissSearch.zh-Hans.md) 操作以编程方式停用该界面。例如，考虑一个带有 [Button](Button.zh-Hans.md) 的视图，该视图显示集合中第一个匹配项的更多信息：

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
    var searchText: String

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

只有在用户输入搜索文本并产生匹配项后，按钮才会显示。按钮的操作会显示一个包含项目详细信息的表格，其中包括一个“添加”按钮，用于将项目添加到已存储的项目列表中：

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

用户可以向下拖动表格来关闭它，从而有效地取消操作，但不会中断正在进行的搜索交互。或者，他们可以点击“添加”按钮来保存项目。由于用户此时可能已经完成了详细信息视图和搜索交互，因此按钮的闭包使用 [dismiss](EnvironmentValues/dismiss.zh-Hans.md) 属性来关闭表格，并使用 [dismissSearch](EnvironmentValues/dismissSearch.zh-Hans.md) 属性来重置搜索字段。

与 `isSearching` 属性一样，请确保仅在可搜索视图修饰符的层级结构内读取 `dismissSearch` 属性。如果在该上下文之外的环境中读取该属性，则调用此操作无效。上述示例从 `SearchedView` 读取操作，并将其传递给工作表，因为工作表有其自身的环境。如果搜索界面未激活，则该操作无效。

### 响应搜索提交

要指定 SwiftUI 在用户提交搜索查询（按下回车键）时调用的操作，请添加 [onSubmit(of:_:)](View/onSubmit_of.zh-Hans.md) 修饰符：

```swift
SearchedView()
    .searchable(text: $searchText)
    .onSubmit(of: .search) {
        submitCurrentSearchQuery()
    }
```

根据应用程序的结构，您可以以不同的方式使用搜索提交。例如，您可以借此机会在搜索查询字符串中查找子字符串，并将其转换为标记。或者，对于速度非常慢的搜索操作（例如，由于需要网络访问），您可以等待提交事件发生后再执行搜索。

## 检测、激活和关闭搜索

- **isSearching**：一个布尔值，指示用户何时正在搜索。

- **dismissSearch**：结束当前搜索交互的操作。

- **DismissSearchAction**：可以结束搜索交互的操作。

- **searchable(text:isPresented:placement:prompt:)**：将此视图标记为可搜索，并以编程方式显示搜索字段。

- **searchable(text:tokens:isPresented:placement:prompt:token:)**：将此视图标记为可搜索，支持文本和词元搜索，并支持编程方式显示。

- **searchable(text:editableTokens:isPresented:placement:prompt:token:)**：将此视图标记为可搜索，并配置搜索字段的显示。

- **searchable(text:tokens:suggestedTokens:isPresented:placement:prompt:token:)**：将此视图标记为可搜索，支持文本、词元和搜索建议，并支持编程方式显示。


---
source: https://developer.apple.com/documentation/SwiftUI/Managing-search-interface-activation
crawled: 2025-12-02T17:31:45Z
---

# Managing search interface activation

**Article**

Programmatically detect and dismiss a search field.

## Overview

People activate a search field in your app by tapping or clicking it, after which they can enter search terms. In many cases, your app only needs to react to the corresponding changes in the search text values, which the interface updates through the binding that you provide, as described in [Performing-a-search-operation](Performing-a-search-operation.zh-Hans.md).

However, SwiftUI also provides controls that enable you to programmatically manage the search interface. In particular, you can:

- Activate or deactivate the interface using a binding that you provide to the searchable modifier.
- Detect whether the interface is active by reading an environment value.
- Dismiss the interface by calling an action stored in the environment.
- Wait for a search submission event before starting to search.

### Control activation through a binding

You can control search interface activation programmatically by providing the searchable modifier’s `isPresented` parameter with a [Binding](Binding.zh-Hans.md) to a Boolean value. For example, to present a sheet that appears with the search interface already active, create a binding that starts as true:

```swift
struct SheetView: View {
    @State private var isPresented = true
    @State private var text = ""
  
    var body: some View {
        NavigationStack {
            SheetContent()
                .searchable(text: $text, isPresented: $isPresented)
        }
    }
}   
```

On iOS and macOS, SwiftUI focuses the search field when presenting search and unfocuses the search field when dismissing search. The search field can also lose focus while the search interface remains presented. For example, if your search interface contains a list of text fields, someone might move focus to one of the text fields without dismissing the interface.

### Detect search activation

If you need to know when the search interface is active, you can query the environment’s [isSearching](EnvironmentValues/isSearching.zh-Hans.md) property using the [Environment](Environment.zh-Hans.md) property wrapper. The following example shows a view that updates the text it displays based on the state of the property:

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
        Text(isSearching ? "Searching" : "Not searching")
    }
}
```

When someone first taps or clicks in a search field, the `isSearching` property becomes `true`. When they cancel the search operation, the property becomes `false`. It also becomes `false` if you programmatically dismiss the interface, as the next section describes.

Be sure to read the property from inside a view that’s wrapped, either directly or indirectly, by one of the [searchable(text:placement:prompt:)](View/searchable_text_placement_prompt.zh-Hans.md) view modifiers, like `SearchedView` in the above example. You won’t detect any change in the property value if you read it from outside of that context, like if you put it in the `SearchingExample` view.

### Dismiss the search interface

You can programmatically deactivate the interface using the environment’s [dismissSearch](EnvironmentValues/dismissSearch.zh-Hans.md) action. For example, consider a view with a [Button](Button.zh-Hans.md) that presents more information about the first matching item from a collection:

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
    var searchText: String

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

The button becomes visible only after someone enters search text that produces a match. The button’s action shows a sheet that provides more information about the item, including an Add button for adding the item to a stored list of items:

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

People can dismiss the sheet by dragging it down, effectively canceling the operation, leaving the in-progress search interaction intact. Alternatively, They can tap the Add button to store the item. Because people are likely done with both the detail view and the search interaction at this point, the button’s closure uses the [dismiss](EnvironmentValues/dismiss.zh-Hans.md) property to dismiss the sheet, and the [dismissSearch](EnvironmentValues/dismissSearch.zh-Hans.md) property to reset the search field.

As with the `isSearching` property, be sure to only read `dismissSearch` from within the hierarchy of a searchable view modifier. Calling the action has no effect if you read it from the environment outside of that context. The above example reads the action from `SearchedView`, and passes that into the sheet, because the sheet has its own environment. The action also has no effect if the search interface isn’t active.

### React to search submission

To specify an action that SwiftUI invokes when someone submits the search query (by pressing the Return key), add the [onSubmit(of:_:)](View/onSubmit_of.zh-Hans.md) modifier:

```swift
SearchedView()
    .searchable(text: $searchText)
    .onSubmit(of: .search) {
        submitCurrentSearchQuery()
    }
```

Depending your app’s structure, you can use search submission in different ways. For example, you can take that opportunity to look for substrings among the search query string that you can convert into tokens. Alternatively, for a search operation that’s very slow, perhaps because it requires a network access, you can wait for a submission event before performing a search.

## Detecting, activating, and dismissing search

- **isSearching**: A Boolean value that indicates when the user is searching.
- **dismissSearch**: An action that ends the current search interaction.
- **DismissSearchAction**: An action that can end a search interaction.
- **searchable(text:isPresented:placement:prompt:)**: Marks this view as searchable with programmatic presentation of the search field.
- **searchable(text:tokens:isPresented:placement:prompt:token:)**: Marks this view as searchable with text and tokens, as well as programmatic presentation.
- **searchable(text:editableTokens:isPresented:placement:prompt:token:)**: Marks this view as searchable, which configures the display of a search field.
- **searchable(text:tokens:suggestedTokens:isPresented:placement:prompt:token:)**: Marks this view as searchable with text, tokens, and suggestions, as well as programmatic presentation.

