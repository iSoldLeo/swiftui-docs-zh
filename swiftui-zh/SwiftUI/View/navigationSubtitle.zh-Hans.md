--- 来源：https://developer.apple.com/documentation/SwiftUI/View/navigationSubtitle(_:)

抓取时间：2025-11-30T21:14:38Z

---

# navigationSubtitle(_:)

**实例方法**

配置视图的导航副标题。

## 声明

```swift
nonisolated func navigationSubtitle(_ subtitle: Text) -> some View

```

## 参数

- **subtitle**：要显示的副标题。

## 说明

视图的导航副标题用于在导航标题旁边提供额外的上下文信息。在 macOS 上，主目标页面的副标题会与导航标题一起显示在标题栏中。在 iOS 和 iPadOS 上，副标题会与导航标题一起显示在导航栏中。

## 设置导航内容标题

- **navigationTitle(_:)**：使用字符串绑定配置视图的导航标题。

- **navigationDocument(_:)**：配置视图的导航文档。

- **navigationDocument(_:preview:)**：配置视图的导航文档。


---
source: https://developer.apple.com/documentation/SwiftUI/View/navigationSubtitle(_:)
crawled: 2025-11-30T21:14:38Z
---

# navigationSubtitle(_:)

**Instance Method**

Configures the view’s subtitle for purposes of navigation.

## Declaration

```swift
nonisolated func navigationSubtitle(_ subtitle: Text) -> some View

```

## Parameters

- **subtitle**: The subtitle to display.

## Discussion

A view’s navigation subtitle is used to provide additional contextual information alongside the navigation title. On macOS, the primary destination’s subtitle is displayed with the navigation title in the titlebar. On iOS and iPadOS, the subtitle is displayed with the navigation title in the navigation bar.

## Setting titles for navigation content

- **navigationTitle(_:)**: Configures the view’s title for purposes of navigation, using a string binding.
- **navigationDocument(_:)**: Configures the view’s document for purposes of navigation.
- **navigationDocument(_:preview:)**: Configures the view’s document for purposes of navigation.

