--- 来源：https://developer.apple.com/documentation/SwiftUI/View/searchToolbarBehavior(_:)

抓取时间：2025-11-30T21:10:26Z

---

# searchToolbarBehavior(_:)

**实例方法**

配置工具栏中搜索的行为。

## 声明

```swift
nonisolated func searchToolbarBehavior(_ behavior: SearchToolbarBehavior) -> some View

```

## 说明

此修饰符可用于更改工具栏中搜索框的默认行为。请将此修饰符置于用于渲染工具栏中搜索框的 [searchable(text:isPresented:placement:prompt:)](searchable_text_isPresented_placement_prompt.zh-Hans.md) 修饰符之后。

在 iPhone 上，可以将底部工具栏中的搜索框配置为在非活动状态下显示为按钮状控件：

```swift
@State private var searchText = ""

NavigationStack {
    RecipeList()
        .searchable($searchText)
        .searchToolbarBehavior(.minimized)
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/View/searchToolbarBehavior(_:)
crawled: 2025-11-30T21:10:26Z
---

# searchToolbarBehavior(_:)

**Instance Method**

Configures the behavior for search in the toolbar.

## Declaration

```swift
nonisolated func searchToolbarBehavior(_ behavior: SearchToolbarBehavior) -> some View

```

## Discussion

This modifier can be used to change the default behavior of a search field that appears in the toolbar. Place this modifier after the [searchable(text:isPresented:placement:prompt:)](searchable_text_isPresented_placement_prompt.zh-Hans.md) modifier that renders search in the toolbar.

On iPhone, the search field in the bottom toolbar can be configured to appear as a button-like control when inactive:

```swift
@State private var searchText = ""

NavigationStack {
    RecipeList()
        .searchable($searchText)
        .searchToolbarBehavior(.minimized)
}
```

