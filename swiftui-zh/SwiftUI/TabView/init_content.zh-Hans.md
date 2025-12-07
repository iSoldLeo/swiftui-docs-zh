---
来源： https://developer.apple.com/documentation/SwiftUI/TabView/init(内容：)
抓取时间： 2025-12-01T00:43:35Z
---

# init(content:)

**Initializer**

创建使用创建器创建标签的标签视图。

## 声明

```swift
init<C>(@TabContentBuilder<Never> content: () -> C) where SelectionValue == Never, Content == TabContentBuilder<Never>.Content<C>, C : TabContent
```

## 参数

- **content**：[Tab](../Tab.zh-Hans.md)的内容。

## 创建标签视图

- **init(selection:content:)**：创建标签视图，该视图使用创建器为其标签创建和指定选择值。


---
source: https://developer.apple.com/documentation/SwiftUI/TabView/init(content:)
crawled: 2025-12-01T00:43:35Z
---

# init(content:)

**Initializer**

Creates a tab view that uses a builder to create its tabs.

## Declaration

```swift
init<C>(@TabContentBuilder<Never> content: () -> C) where SelectionValue == Never, Content == TabContentBuilder<Never>.Content<C>, C : TabContent
```

## Parameters

- **content**: The [Tab](../Tab.zh-Hans.md) content.

## Creating a tab view

- **init(selection:content:)**: Creates a tab view that uses a builder to create and specify selection values for its tabs.

