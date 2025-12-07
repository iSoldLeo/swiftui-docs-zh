--- 来源：https://developer.apple.com/documentation/SwiftUI/View/navigationDocument(_:preview:)

抓取时间：2025-12-02T17:29:35Z

---

# navigationDocument(_:preview:)

**实例方法**

配置视图的文档以用于导航。

## 声明

```swift
nonisolated func navigationDocument<D, I1, I2>(_ document: D, preview: SharePreview<I1, I2>) -> some View where D : Transferable, I1 : Transferable, I2 : Transferable

```

## 参数

- **document**：与导航标题关联的可传输内容。

- **preview**：共享时要使用的文档预览。

## 说明

在 iOS 和 iPadOS 中，此方法会在标题菜单中填充一个预览文档的标题。在 macOS 中，此方法会填充一个代理图标。

有关导航文档修饰符的更多信息，请参阅 [Configure-Your-Apps-Navigation-Titles](../Configure-Your-Apps-Navigation-Titles.zh-Hans.md) 文章。

## 设置导航内容标题

- **navigationTitle(_:)**：使用字符串绑定配置视图的导航标题。

- **navigationSubtitle(_:)**：配置视图的导航副标题。

- **navigationDocument(_:)**：配置视图的导航文档。


---
source: https://developer.apple.com/documentation/SwiftUI/View/navigationDocument(_:preview:)
crawled: 2025-12-02T17:29:35Z
---

# navigationDocument(_:preview:)

**Instance Method**

Configures the view’s document for purposes of navigation.

## Declaration

```swift
nonisolated func navigationDocument<D, I1, I2>(_ document: D, preview: SharePreview<I1, I2>) -> some View where D : Transferable, I1 : Transferable, I2 : Transferable

```

## Parameters

- **document**: The transferable content associated to the navigation title.
- **preview**: The preview of the document to use when sharing.

## Discussion

In iOS, iPadOS, this populates the title menu with a header previewing the document. In macOS, this populates a proxy icon.

Refer to the [Configure-Your-Apps-Navigation-Titles](../Configure-Your-Apps-Navigation-Titles.zh-Hans.md) article for more information on navigation document modifiers.

## Setting titles for navigation content

- **navigationTitle(_:)**: Configures the view’s title for purposes of navigation, using a string binding.
- **navigationSubtitle(_:)**: Configures the view’s subtitle for purposes of navigation.
- **navigationDocument(_:)**: Configures the view’s document for purposes of navigation.

