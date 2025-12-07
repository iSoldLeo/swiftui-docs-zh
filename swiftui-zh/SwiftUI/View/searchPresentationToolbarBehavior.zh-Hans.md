--- 来源：https://developer.apple.com/documentation/SwiftUI/View/searchPresentationToolbarBehavior(_:)

抓取时间：2025-11-30T21:16:56Z

---

# searchPresentationToolbarBehavior(_:)

**实例方法**

配置此视图中所有可搜索修饰符的搜索工具栏显示行为。

## 声明

```swift
nonisolated func searchPresentationToolbarBehavior(_ behavior: SearchPresentationToolbarBehavior) -> some View

```

## 讨论

在 iOS 系统中，工具栏在显示搜索时可能会隐藏部分内容，以便用户专注于搜索。您可以通过为该修饰符提供 [avoidHidingContent](../SearchPresentationToolbarBehavior/avoidHidingContent.zh-Hans.md) 值来覆盖此行为。

```swift
@State private var searchText = ""

List {
    // ... content
}
.searchable(text: $searchText)
.searchPresentationToolbarBehavior(.avoidHidingContent)
```

## 搜索期间显示工具栏内容

- **SearchPresentationToolbarBehavior**：定义工具栏在显示搜索时的行为方式的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/View/searchPresentationToolbarBehavior(_:)
crawled: 2025-11-30T21:16:56Z
---

# searchPresentationToolbarBehavior(_:)

**Instance Method**

Configures the search toolbar presentation behavior for any searchable modifiers within this view.

## Declaration

```swift
nonisolated func searchPresentationToolbarBehavior(_ behavior: SearchPresentationToolbarBehavior) -> some View

```

## Discussion

By default on iOS, a toolbar may hide parts of its content when presenting search to focus on searching. You can override this behavior by providing a value of [avoidHidingContent](../SearchPresentationToolbarBehavior/avoidHidingContent.zh-Hans.md) to this modifer.

```swift
@State private var searchText = ""

List {
    // ... content
}
.searchable(text: $searchText)
.searchPresentationToolbarBehavior(.avoidHidingContent)
```

## Displaying toolbar content during search

- **SearchPresentationToolbarBehavior**: A type that defines how the toolbar behaves when presenting search.

