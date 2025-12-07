---
来源： https://developer.apple.com/documentation/SwiftUI/SearchFieldPlacement
抓取时间： 2025-12-02T17:31:34Z
---

# SearchFieldPlacement

**Structure**

搜索字段在视图层次结构中的位置。

## 声明

```swift
struct SearchFieldPlacement
```

## 概览

您可以为任何可搜索修饰符指定优先位置，如 [searchable(text:placement:prompt:)](View/searchable_text_placement_prompt.zh-Hans.md)：

```swift
var body: some View {
    NavigationView {
        PrimaryView()
        SecondaryView()
        Text("Select a primary and secondary item")
    }
    .searchable(text: $text, placement: .sidebar)
}
```

根据包含视图的层级，SwiftUI 可能无法满足您的请求。

## 获取搜索字段位置

- **automatic**：SwiftUI 会自动放置搜索栏。
- **navigationBarDrawer**：搜索栏显示在导航栏中。
- **navigationBarDrawer(displayMode:)**：使用指定的显示模式在导航栏中显示搜索字段。
- **sidebar**：搜索栏显示在导航视图的侧边栏中。
- **toolbar**：搜索字段出现在工具栏中。

## 支持类型

- **SearchFieldPlacement.NavigationBarDrawerDisplayMode**：决定何时显示导航栏中搜索字段的模式。

## 类型属性

- **toolbarPrincipal**：搜索栏显示在工具栏的主要部分。

## 搜索应用程序的数据模型

- 在应用程序中添加搜索界面**：提供一个界面，供用户搜索应用程序中的内容。
- 执行搜索操作**：根据搜索文本和您存储的可选标记更新搜索结果。
- **searchable(text:placement:prompt:)**：将此视图标记为可搜索，从而配置搜索字段的显示。
- **searchable(text:tokens:placement:prompt:token:)**：将此视图标记为可使用文本和标记符搜索。
- **searchable(text:editableTokens:placement:prompt:token:)**：将此视图标记为可搜索，并配置显示搜索字段。

## 符合

- 可发送
- 可发送类型


---
source: https://developer.apple.com/documentation/SwiftUI/SearchFieldPlacement
crawled: 2025-12-02T17:31:34Z
---

# SearchFieldPlacement

**Structure**

The placement of a search field in a view hierarchy.

## Declaration

```swift
struct SearchFieldPlacement
```

## Overview

You can give a preferred placement to any of the searchable modifiers, like [searchable(text:placement:prompt:)](View/searchable_text_placement_prompt.zh-Hans.md):

```swift
var body: some View {
    NavigationView {
        PrimaryView()
        SecondaryView()
        Text("Select a primary and secondary item")
    }
    .searchable(text: $text, placement: .sidebar)
}
```

Depending on the containing view hierachy, SwiftUI might not be able to fulfill your request.

## Getting a search field placement

- **automatic**: SwiftUI places the search field automatically.
- **navigationBarDrawer**: The search field appears in the navigation bar.
- **navigationBarDrawer(displayMode:)**: The search field appears in the navigation bar using the specified display mode.
- **sidebar**: The search field appears in the sidebar of a navigation view.
- **toolbar**: The search field appears in the toolbar.

## Supporting types

- **SearchFieldPlacement.NavigationBarDrawerDisplayMode**: A mode that determines when to display a search field that appears in a navigation bar.

## Type Properties

- **toolbarPrincipal**: The search field appears in the principal section of the toolbar.

## Searching your app’s data model

- **Adding a search interface to your app**: Present an interface that people can use to search for content in your app.
- **Performing a search operation**: Update search results based on search text and optional tokens that you store.
- **searchable(text:placement:prompt:)**: Marks this view as searchable, which configures the display of a search field.
- **searchable(text:tokens:placement:prompt:token:)**: Marks this view as searchable with text and tokens.
- **searchable(text:editableTokens:placement:prompt:token:)**: Marks this view as searchable, which configures the display of a search field.

## Conforms To

- Sendable
- SendableMetatype

