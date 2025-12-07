--- 来源：https://developer.apple.com/documentation/SwiftUI/Search
抓取时间：2025-12-02T17:20:47Z

---

# 搜索

**API 集合**

让用户能够在您的应用内搜索文本或其他内容。

## 概述

要在应用中显示搜索框，您需要创建并管理用于存储搜索文本的存储空间，以及（可选的）用于存储称为“词元”的离散搜索词的存储空间。然后，通过将可搜索视图修饰符应用于应用中的某个视图，将存储空间绑定到搜索框。

当用户与搜索框交互时，他们会隐式地修改底层存储空间，从而修改搜索参数。您的应用会相应地更新其界面的其他部分。为了增强搜索交互体验，您还可以：

- 在搜索过程中提供建议，支持文本和词元搜索。

- 实现搜索范围，帮助用户缩小搜索范围。

- 检测用户何时激活搜索框，并使用环境变量以编程方式关闭搜索框。

设计指南请参见《人机界面指南》中的 [doc://com.apple.documentation/design/Human-Interface-Guidelines/searching]。

## 搜索应用的数据模型

- **向应用添加搜索界面**：提供一个界面，供用户搜索应用内的内容。

- **执行搜索操作**：根据搜索文本和您存储的可选标记更新搜索结果。

- **searchable(text:placement:prompt:)**：将此视图标记为可搜索，从而配置搜索字段的显示。

- **searchable(text:tokens:placement:prompt:token:)**：将此视图标记为可使用文本和标记进行搜索。

- **searchable(text:editableTokens:placement:prompt:token:)**：将此视图标记为可搜索，从而配置搜索字段的显示。

- **SearchFieldPlacement**：在视图层次结构中放置搜索字段。

## 提供搜索建议

- **建议搜索词**：为在应用中搜索内容的用户提供建议。

- **searchSuggestions(_:)**：配置此视图的搜索建议。

- **searchSuggestions(_:for:)**：配置在此视图中显示搜索建议的方式。

- **searchCompletion(_:)**：将一个完整的字符串与此视图的值关联起来，以便用作搜索建议。

- **searchable(text:tokens:suggestedTokens:placement:prompt:token:)**：将此视图标记为可搜索，支持文本、词元和建议。

- **SearchSuggestionsPlacement**：SwiftUI 显示搜索建议的方式。

## 限制搜索范围

- **限定搜索范围**：将搜索范围划分为几个大类。

- **searchScopes(_:scopes:)**：配置此视图的搜索范围。

- **searchScopes(_:activation:_:)**：使用指定的激活策略配置此视图的搜索范围。

- **SearchScopeActivation**：可搜索修饰符显示或隐藏搜索范围的方式。

## 检测、激活和关闭搜索

- **管理搜索界面激活**：以编程方式检测和关闭搜索字段。

- **isSearching**：指示用户何时正在搜索的布尔值。

- **dismissSearch**：结束当前搜索交互的操作。

- **DismissSearchAction**：可以结束搜索交互的操作。

- **searchable(text:isPresented:placement:prompt:)**：将此视图标记为可搜索，并以编程方式显示搜索字段。

- **searchable(text:tokens:isPresented:placement:prompt:token:)**：将此视图标记为可搜索，支持文本和词条搜索，并支持程序化显示。

- **searchable(text:editableTokens:isPresented:placement:prompt:token:)**：将此视图标记为可搜索，并配置搜索字段的显示。

- **searchable(text:tokens:suggestedTokens:isPresented:placement:prompt:token:)**：将此视图标记为可搜索，支持文本、词条和搜索建议，并支持程序化显示。

## 搜索期间显示工具栏内容

- **searchPresentationToolbarBehavior(_:)**：配置此视图中任何可搜索修饰符的搜索工具栏显示行为。

- **SearchPresentationToolbarBehavior**：定义工具栏在显示搜索时的行为方式的类型。

## 在视图中搜索文本

- **findNavigator(isPresented:)**：以程序化方式显示文本编辑器视图的查找和替换界面。

- **findDisabled(_:)**：阻止在文本编辑器中执行查找和替换操作。

- **replaceDisabled(_:)**：阻止在文本编辑器中执行替换操作。

- **FindContext**：支持文本编辑的视图的查找导航器状态。

## 应用结构

- **应用组织结构**：定义应用的入口点和顶级结构。

- **Scenes**：声明构成应用各个部分的用户界面分组。

- **Windows**：在单个窗口或窗口集合中显示用户界面内容。

- **沉浸式空间**：在用户的周围环境中显示无限内容。

- **Documents**：允许用户打开和管理文档。

- **Navigation**：允许用户在场景内于应用视图层级结构的不同部分之间切换。

- **模态呈现**：在单独的视图中呈现内容，提供更集中的交互体验。

- **Toolbars**：提供对常用命令和控件的快速访问。

- **应用扩展**：将应用的基本功能扩展到系统的其他部分，例如通过添加小部件。


---
source: https://developer.apple.com/documentation/SwiftUI/Search
crawled: 2025-12-02T17:20:47Z
---

# Search

**API Collection**

Enable people to search for text or other content within your app.

## Overview

To present a search field in your app, create and manage storage for search text and optionally for discrete search terms known as *tokens*. Then bind the storage to the search field by applying the searchable view modifier to a view in your app.



As people interact with the field, they implicitly modify the underlying storage and, thereby, the search parameters. Your app correspondingly updates other parts of its interface. To enhance the search interaction, you can also:

- Offer suggestions during search, for both text and tokens.
- Implement search scopes that help people to narrow the search space.
- Detect when people activate the search field, and programmatically dismiss the search field using environment values.

For design guidance, see [doc://com.apple.documentation/design/Human-Interface-Guidelines/searching] in the Human Interface Guidelines.

## Searching your app’s data model

- **Adding a search interface to your app**: Present an interface that people can use to search for content in your app.
- **Performing a search operation**: Update search results based on search text and optional tokens that you store.
- **searchable(text:placement:prompt:)**: Marks this view as searchable, which configures the display of a search field.
- **searchable(text:tokens:placement:prompt:token:)**: Marks this view as searchable with text and tokens.
- **searchable(text:editableTokens:placement:prompt:token:)**: Marks this view as searchable, which configures the display of a search field.
- **SearchFieldPlacement**: The placement of a search field in a view hierarchy.

## Making search suggestions

- **Suggesting search terms**: Provide suggestions to people searching for content in your app.
- **searchSuggestions(_:)**: Configures the search suggestions for this view.
- **searchSuggestions(_:for:)**: Configures how to display search suggestions within this view.
- **searchCompletion(_:)**: Associates a fully formed string with the value of this view when used as a search suggestion.
- **searchable(text:tokens:suggestedTokens:placement:prompt:token:)**: Marks this view as searchable with text, tokens, and suggestions.
- **SearchSuggestionsPlacement**: The ways that SwiftUI displays search suggestions.

## Limiting search scope

- **Scoping a search operation**: Divide the search space into a few broad categories.
- **searchScopes(_:scopes:)**: Configures the search scopes for this view.
- **searchScopes(_:activation:_:)**: Configures the search scopes for this view with the specified activation strategy.
- **SearchScopeActivation**: The ways that searchable modifiers can show or hide search scopes.

## Detecting, activating, and dismissing search

- **Managing search interface activation**: Programmatically detect and dismiss a search field.
- **isSearching**: A Boolean value that indicates when the user is searching.
- **dismissSearch**: An action that ends the current search interaction.
- **DismissSearchAction**: An action that can end a search interaction.
- **searchable(text:isPresented:placement:prompt:)**: Marks this view as searchable with programmatic presentation of the search field.
- **searchable(text:tokens:isPresented:placement:prompt:token:)**: Marks this view as searchable with text and tokens, as well as programmatic presentation.
- **searchable(text:editableTokens:isPresented:placement:prompt:token:)**: Marks this view as searchable, which configures the display of a search field.
- **searchable(text:tokens:suggestedTokens:isPresented:placement:prompt:token:)**: Marks this view as searchable with text, tokens, and suggestions, as well as programmatic presentation.

## Displaying toolbar content during search

- **searchPresentationToolbarBehavior(_:)**: Configures the search toolbar presentation behavior for any searchable modifiers within this view.
- **SearchPresentationToolbarBehavior**: A type that defines how the toolbar behaves when presenting search.

## Searching for text in a view

- **findNavigator(isPresented:)**: Programmatically presents the find and replace interface for text editor views.
- **findDisabled(_:)**: Prevents find and replace operations in a text editor.
- **replaceDisabled(_:)**: Prevents replace operations in a text editor.
- **FindContext**: The status of the find navigator for views which support text editing.

## App structure

- **App organization**: Define the entry point and top-level structure of your app.
- **Scenes**: Declare the user interface groupings that make up the parts of your app.
- **Windows**: Display user interface content in a window or a collection of windows.
- **Immersive spaces**: Display unbounded content in a person’s surroundings.
- **Documents**: Enable people to open and manage documents.
- **Navigation**: Enable people to move between different parts of your app’s view hierarchy within a scene.
- **Modal presentations**: Present content in a separate view that offers focused interaction.
- **Toolbars**: Provide immediate access to frequently used commands and controls.
- **App extensions**: Extend your app’s basic functionality to other parts of the system, like by adding a Widget.

