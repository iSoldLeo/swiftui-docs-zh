--- 来源：https://developer.apple.com/documentation/SwiftUI/View/navigationTitle(_:)

抓取时间：2025-11-30T21:14:37Z

---

# navigationTitle(_:)

**实例方法**

使用字符串绑定配置视图的导航标题。

## 声明

```swift
nonisolated func navigationTitle(_ title: Binding<String>) -> some View

```

## 参数

- **title**：标题文本。

## 说明

在 iOS、iPadOS 和 macOS 中，当导航标题显示在工具栏中时，此方法允许编辑导航标题。

有关导航标题修饰符的更多信息，请参阅 [Configure-Your-Apps-Navigation-Titles](../Configure-Your-Apps-Navigation-Titles.zh-Hans.md) 文章。

## 设置导航内容标题

- **navigationSubtitle(_:)**：配置视图的副标题，用于导航。

- **navigationDocument(_:)**：配置视图的文档，用于导航。

- **navigationDocument(_:preview:)**：配置视图的文档，用于导航。


---
source: https://developer.apple.com/documentation/SwiftUI/View/navigationTitle(_:)
crawled: 2025-11-30T21:14:37Z
---

# navigationTitle(_:)

**Instance Method**

Configures the view’s title for purposes of navigation, using a string binding.

## Declaration

```swift
nonisolated func navigationTitle(_ title: Binding<String>) -> some View

```

## Parameters

- **title**: The text of the title.

## Discussion

In iOS, iPadOS, and macOS, this allows editing the navigation title when the title is displayed in the toolbar.

Refer to the [Configure-Your-Apps-Navigation-Titles](../Configure-Your-Apps-Navigation-Titles.zh-Hans.md) article for more information on navigation title modifiers.

## Setting titles for navigation content

- **navigationSubtitle(_:)**: Configures the view’s subtitle for purposes of navigation.
- **navigationDocument(_:)**: Configures the view’s document for purposes of navigation.
- **navigationDocument(_:preview:)**: Configures the view’s document for purposes of navigation.

