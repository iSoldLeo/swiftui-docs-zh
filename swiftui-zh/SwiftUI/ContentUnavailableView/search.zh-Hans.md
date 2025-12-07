--- 来源：https://developer.apple.com/documentation/SwiftUI/ContentUnavailableView/search

抓取时间：2025-12-03T04:16:34Z

---

# 搜索

**类型属性**

创建一个 `ContentUnavailableView` 实例，用于表示搜索状态。

## 声明

```swift
static var search: ContentUnavailableView<SearchUnavailableContent.Label, SearchUnavailableContent.Description, SearchUnavailableContent.Actions> { get }
```

## 说明

使用此静态成员初始化的 `ContentUnavailableView` 实例应包含在可搜索的视图层级结构中。这样的配置可以将搜索查询解析为视图的描述。

例如，考虑一下 *ContactsListView* 中这个静态成员的用法：

```swift
struct ContactsListView: View {
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

## 获取内置的不可用视图

- **search(text:)**：创建一个 `ContentUnavailableView` 实例，用于表示搜索状态。


---
source: https://developer.apple.com/documentation/SwiftUI/ContentUnavailableView/search
crawled: 2025-12-03T04:16:34Z
---

# search

**Type Property**

Creates a `ContentUnavailableView` instance that conveys a search state.

## Declaration

```swift
static var search: ContentUnavailableView<SearchUnavailableContent.Label, SearchUnavailableContent.Description, SearchUnavailableContent.Actions> { get }
```

## Discussion

A `ContentUnavailableView` initialized with this static member is expected to be contained within a searchable view hierarchy. Such a configuration enables the search query to be parsed into the view’s description.

For example, consider the usage of this static member in *ContactsListView*:

```swift
struct ContactsListView: View {
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

- **search(text:)**: Creates a `ContentUnavailableView` instance that conveys a search state.

