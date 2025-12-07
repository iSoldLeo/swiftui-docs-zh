---
来源：https://developer.apple.com/documentation/swiftui/tabview/init(selection:content:)
抓取时间： 2025-12-02T16:16:17Z
---

# init(selection:content:)

**Initializer**

创建标签视图，该视图使用创建器为其标签创建和指定选择值。

## 声明

```swift
init<C>(selection: Binding<SelectionValue>, @TabContentBuilder<SelectionValue> content: () -> C) where Content == TabContentBuilder<SelectionValue>.Content<C>, C : TabContent
```

## 参数

- **selection**：TabView 中的选择。此绑定的值必须与`value` 中标签页的`content` 匹配。
- **content**：[Tab](../Tab.zh-Hans.md)的内容。

## 创建标签视图

- **init(content:)**：创建使用创建器创建标签的标签视图。


---
source: https://developer.apple.com/documentation/swiftui/tabview/init(selection:content:)
crawled: 2025-12-02T16:16:17Z
---

# init(selection:content:)

**Initializer**

Creates a tab view that uses a builder to create and specify selection values for its tabs.

## Declaration

```swift
init<C>(selection: Binding<SelectionValue>, @TabContentBuilder<SelectionValue> content: () -> C) where Content == TabContentBuilder<SelectionValue>.Content<C>, C : TabContent
```

## Parameters

- **selection**: The selection in the TabView. The value of this binding must match the `value` of the tabs in `content`.
- **content**: The [Tab](../Tab.zh-Hans.md) content.

## Creating a tab view

- **init(content:)**: Creates a tab view that uses a builder to create its tabs.

