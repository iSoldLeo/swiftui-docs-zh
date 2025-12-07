--- 来源：https://developer.apple.com/documentation/SwiftUI/ContentUnavailableView/search(text:)

抓取时间：2025-12-01T09:06:02Z

---

# search(text:)

**类型方法**

创建一个 `ContentUnavailableView` 实例，用于表示搜索状态。

## 声明

```swift
static func search(text: String) -> ContentUnavailableView<Label, Description, Actions>
```

## 参数

- **text**：搜索文本查询。

## 讨论

例如，考虑在 *ContactsListView* 中使用此静态成员：

```swift
struct ContactsListView: View {
    @ObservedObject private var viewModel = ContactsViewModel()

    var body: some View {
        NavigationStack {
            CustomSearchBar(query: $viewModel.searchText)
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
            .overlay {
                if viewModel.searchResults.isEmpty {
                    ContentUnavailableView
                        .search(text: viewModel.searchText)
                }
            }
        }
    }
}
```

## 获取内置的不可用视图

- **search**：创建一个 `ContentUnavailableView` 实例，用于表示搜索状态。


---
source: https://developer.apple.com/documentation/SwiftUI/ContentUnavailableView/search(text:)
crawled: 2025-12-01T09:06:02Z
---

# search(text:)

**Type Method**

Creates a `ContentUnavailableView` instance that conveys a search state.

## Declaration

```swift
static func search(text: String) -> ContentUnavailableView<Label, Description, Actions>
```

## Parameters

- **text**: The search text query.

## Discussion

For example, consider the usage of this static member in *ContactsListView*:

```swift
struct ContactsListView: View {
    @ObservedObject private var viewModel = ContactsViewModel()

    var body: some View {
        NavigationStack {
            CustomSearchBar(query: $viewModel.searchText)
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
            .overlay {
                if viewModel.searchResults.isEmpty {
                    ContentUnavailableView
                        .search(text: viewModel.searchText)
                }
            }
        }
    }
}
```

## Getting built-in unavailable views

- **search**: Creates a `ContentUnavailableView` instance that conveys a search state.

