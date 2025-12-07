--- 来源：https://developer.apple.com/documentation/SwiftUI/SubmitTriggers/search
抓取时间：2025-12-03T06:45:59Z

---

# 搜索

**类型属性**

定义由可搜索修饰符构建的搜索字段触发的触发器。

## 声明

```swift
static let search: SubmitTriggers
```

## 说明

在下面的示例中，只有由可搜索修饰符放置的搜索字段或搜索补全项才会触发视图模型提交其当前搜索查询。

```swift
@StateObject private var viewModel = ViewModel()

NavigationView {
    SidebarView()
    DetailView()
}
.searchable(
    text: $viewModel.searchText,
    placement: .sidebar
) {
    SuggestionsView()
}
.onSubmit(of: .search) {
    viewModel.submitCurrentSearchQuery()
}
```

## 获取提交触发器

- **text**：定义由文本输入控件（例如 `TextField` 和 `SecureField`）触发的触发器。


---
source: https://developer.apple.com/documentation/SwiftUI/SubmitTriggers/search
crawled: 2025-12-03T06:45:59Z
---

# search

**Type Property**

Defines triggers originating from search fields constructed from searchable modifiers.

## Declaration

```swift
static let search: SubmitTriggers
```

## Discussion

In the example below, only the search field or search completions placed by the searchable modifier will trigger the view model to submit its current search query.

```swift
@StateObject private var viewModel = ViewModel()

NavigationView {
    SidebarView()
    DetailView()
}
.searchable(
    text: $viewModel.searchText,
    placement: .sidebar
) {
    SuggestionsView()
}
.onSubmit(of: .search) {
    viewModel.submitCurrentSearchQuery()
}
```

## Getting submit triggers

- **text**: Defines triggers originating from text input controls like `TextField` and `SecureField`.

