---
来源： https://developer.apple.com/documentation/SwiftUI/ContentUnavailableView
抓取时间： 2025-12-02T17:02:54Z
---

# ContentUnavailableView

**Structure**

当用户无法使用应用程序内容时显示的界面，由标签和附加内容组成。

## 声明

```swift
struct ContentUnavailableView<Label, Description, Actions> where Label : View, Description : View, Actions : View
```

## 概览

建议在无法显示视图内容时使用 `ContentUnavailableView`。造成这种情况的原因可能是网络错误、列表中没有条目、搜索没有返回结果等。

创建⟦IC_0007❾的最简单方法是提供一个标签和一些附加内容，如描述或行动号召：

```swift
ContentUnavailableView {
    Label("No Mail", systemImage: "tray.fill")
} description: {
    Text("New mails you receive will appear here.")
}
```

系统提供了默认的`ContentUnavailableView`，您可以在特定情况下使用。下面的示例说明了[search](ContentUnavailableView/search.zh-Hans.md) 视图的用法：

```swift
struct ContentView: View {
    @ObservedObject private var viewModel = ContactsViewModel()

    var body: some View {
        NavigationStack {
            List {
                ForEach(viewModel.searchResults) { contact in
                    NavigationLink {
                        ContactsView(contact)
                    } label: {
                        Text(contact.name)
                    }
                }
            }
            .navigationTitle("Contacts")
            .searchable(text: $viewModel.searchText)
            .overlay {
                if searchResults.isEmpty {
                    ContentUnavailableView.search
                }
            }
        }
    }
}
```视图

## 获取内置的不可用视图

- **search**：创建传递搜索状态的 `ContentUnavailableView` 实例。
- **search(text:)**：创建传递搜索状态的 `ContentUnavailableView` 实例。

## 创建不可用的视图

- **init(label:description:actions:)**：创建一个由标签和附加内容组成的界面，当用户无法使用应用程序内容时显示该界面。
- **init(_:image:description:)**：创建一个由本地化字符串生成的标题、图像和附加内容组成的界面，当用户无法使用应用程序内容时显示该界面。
- **init(_:systemImage:description:)**：创建由本地化字符串生成的标题、系统图标图像和附加内容组成的界面，当用户无法使用应用程序内容时显示该界面。

## 支持类型

- **SearchUnavailableContent**：表示静态占位符搜索视图主体的结构。

## 符合

- 视图


---
source: https://developer.apple.com/documentation/SwiftUI/ContentUnavailableView
crawled: 2025-12-02T17:02:54Z
---

# ContentUnavailableView

**Structure**

An interface, consisting of a label and additional content, that you display when the content of your app is unavailable to users.

## Declaration

```swift
struct ContentUnavailableView<Label, Description, Actions> where Label : View, Description : View, Actions : View
```

## Overview

It is recommended to use `ContentUnavailableView` in situations where a view’s content cannot be displayed. That could be caused by a network error, a list without items, a search that returns no results etc.

You create an `ContentUnavailableView` in its simplest form, by providing a label and some additional content such as a description or a call to action:

```swift
ContentUnavailableView {
    Label("No Mail", systemImage: "tray.fill")
} description: {
    Text("New mails you receive will appear here.")
}
```

The system provides default `ContentUnavailableView`s that you can use in specific situations. The example below illustrates the usage of the [search](ContentUnavailableView/search.zh-Hans.md) view:

```swift
struct ContentView: View {
    @ObservedObject private var viewModel = ContactsViewModel()

    var body: some View {
        NavigationStack {
            List {
                ForEach(viewModel.searchResults) { contact in
                    NavigationLink {
                        ContactsView(contact)
                    } label: {
                        Text(contact.name)
                    }
                }
            }
            .navigationTitle("Contacts")
            .searchable(text: $viewModel.searchText)
            .overlay {
                if searchResults.isEmpty {
                    ContentUnavailableView.search
                }
            }
        }
    }
}
```

## Getting built-in unavailable views

- **search**: Creates a `ContentUnavailableView` instance that conveys a search state.
- **search(text:)**: Creates a `ContentUnavailableView` instance that conveys a search state.

## Creating an unavailable view

- **init(label:description:actions:)**: Creates an interface, consisting of a label and additional content, that you display when the content of your app is unavailable to users.
- **init(_:image:description:)**: Creates an interface, consisting of a title generated from a localized string, an image and additional content, that you display when the content of your app is unavailable to users.
- **init(_:systemImage:description:)**: Creates an interface, consisting of a title generated from a localized string, a system icon image and additional content, that you display when the content of your app is unavailable to users.

## Supporting types

- **SearchUnavailableContent**: A structure that represents the body of a static placeholder search view.

## Conforms To

- View

