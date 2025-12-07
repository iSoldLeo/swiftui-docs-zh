---
来源： https://developer.apple.com/documentation/SwiftUI/View-Search
抓取时间： 2025-12-02T17:22:16Z
---

# 搜索修改器

**API 集合**

让用户可以搜索应用程序中的内容。

## 概览

使用搜索视图修饰符为您的应用程序添加搜索功能。有关详细信息，请参阅 [Search](Search.zh-Hans.md)。

## 显示搜索界面

- **searchable(text:placement:prompt:)**：将此视图标记为可搜索视图，从而配置显示搜索字段。
- **searchable(text:isPresented:placement:prompt:)**：将此视图标记为可搜索视图，并以编程方式显示搜索字段。
- **searchPresentationToolbarBehavior(_:)**：为该视图中的任何可搜索修饰符配置搜索工具栏显示行为。

## 使用标记搜索

- **searchable(text:tokens:placement:prompt:token:)**：将此视图标记为可使用文本和标记符搜索。
- **searchable(text:tokens:isPresented:placement:prompt:token:)**：将此视图标记为可通过文本和标记符以及程序演示进行搜索。

## 使用可编辑标记符搜索

- **searchable(text:editableTokens:isPresented:placement:prompt:token:)**：将此视图标记为可搜索视图，从而配置显示搜索字段。
- **searchable(text:editableTokens:placement:prompt:token:)**：将此视图标记为可搜索视图，并配置显示搜索字段。

### 提出搜索建议

- **searchSuggestions(_:)**：配置该视图的搜索建议。
- **searchSuggestions(_:for:)**：配置如何在此视图中显示搜索建议。
- **searchCompletion(_:)**：当用作搜索建议时，将一个完整的字符串与此视图的值关联。
- **searchable(text:tokens:suggestedTokens:placement:prompt:token:)**：将此视图标记为可使用文本、标记和建议进行搜索。
- **searchable(text:tokens:suggestedTokens:isPresented:placement:prompt:token:)**：将此视图标记为可通过文本、标记和建议以及程序化展示进行搜索。

## 限制搜索范围

- **searchScopes(_:scopes:)**：配置该视图的搜索范围。
- **searchScopes(_:activation:_:)**：使用指定的激活策略为该视图配置搜索范围。

## 通过口述搜索

- **searchDictationBehavior(_:)**：为可搜索修饰符配置的任何搜索字段配置听写行为。

## 提供交互性

- **输入和事件修改器**：为视图提供响应用户输入和系统事件的操作。
- **呈现修改器**：定义视图在指定条件下显示的其他视图。
- 状态修改器***：访问存储并为子视图提供配置数据。


---
source: https://developer.apple.com/documentation/SwiftUI/View-Search
crawled: 2025-12-02T17:22:16Z
---

# Search modifiers

**API Collection**

Enable people to search for content in your app.

## Overview

Use search view modifiers to add search capability to your app. For more information, see [Search](Search.zh-Hans.md).

## Displaying a search interface

- **searchable(text:placement:prompt:)**: Marks this view as searchable, which configures the display of a search field.
- **searchable(text:isPresented:placement:prompt:)**: Marks this view as searchable with programmatic presentation of the search field.
- **searchPresentationToolbarBehavior(_:)**: Configures the search toolbar presentation behavior for any searchable modifiers within this view.

## Searching with tokens

- **searchable(text:tokens:placement:prompt:token:)**: Marks this view as searchable with text and tokens.
- **searchable(text:tokens:isPresented:placement:prompt:token:)**: Marks this view as searchable with text and tokens, as well as programmatic presentation.

## Searching with editable tokens

- **searchable(text:editableTokens:isPresented:placement:prompt:token:)**: Marks this view as searchable, which configures the display of a search field.
- **searchable(text:editableTokens:placement:prompt:token:)**: Marks this view as searchable, which configures the display of a search field.

## Making search suggestions

- **searchSuggestions(_:)**: Configures the search suggestions for this view.
- **searchSuggestions(_:for:)**: Configures how to display search suggestions within this view.
- **searchCompletion(_:)**: Associates a fully formed string with the value of this view when used as a search suggestion.
- **searchable(text:tokens:suggestedTokens:placement:prompt:token:)**: Marks this view as searchable with text, tokens, and suggestions.
- **searchable(text:tokens:suggestedTokens:isPresented:placement:prompt:token:)**: Marks this view as searchable with text, tokens, and suggestions, as well as programmatic presentation.

## Limiting search scope

- **searchScopes(_:scopes:)**: Configures the search scopes for this view.
- **searchScopes(_:activation:_:)**: Configures the search scopes for this view with the specified activation strategy.

## Searching through dictation

- **searchDictationBehavior(_:)**: Configures the dictation behavior for any search fields configured by the searchable modifier.

## Providing interactivity

- **Input and event modifiers**: Supply actions for a view to perform in response to user input and system events.
- **Presentation modifiers**: Define additional views for the view to present under specified conditions.
- **State modifiers**: Access storage and provide child views with configuration data.

