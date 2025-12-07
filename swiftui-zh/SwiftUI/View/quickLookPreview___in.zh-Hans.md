--- 来源：https://developer.apple.com/documentation/SwiftUI/View/quickLookPreview(_:in:)

抓取时间：2025-12-02T17:45:33Z

---

# quickLookPreview(_:in:)

**实例方法**

快速预览您提供的 URL。

## 声明

```swift
nonisolated func quickLookPreview<Items>(_ selection: Binding<Items.Element?>, in items: Items) -> some View where Items : RandomAccessCollection, Items.Element == URL

```

## 参数

- **selection**：一个指向 items 集合中元素的 [doc://com.apple.documentation/documentation/SwiftUI/Binding]。这是您当前要预览的 URL。

- **items**：要预览的 URL 集合。

## 返回值

一个显示 URL 内容预览的视图。

## 讨论

当您将绑定项设置为非 `nil` 项时，会显示“快速查看”预览。当您将项设置回 `nil` 时，“快速查看”预览将关闭。如果选择绑定的值不在项集合中，“快速查看”将其视为 `nil` 选择。

“快速查看”会将选择绑定的值更新为与用户正在预览的文件 URL 匹配。用户关闭预览后，“快速查看”会自动将项绑定设置为 `nil`。

## 预览内容

- **quickLookPreview(_:)**：显示单个 URL 内容的“快速查看”预览。


---
source: https://developer.apple.com/documentation/SwiftUI/View/quickLookPreview(_:in:)
crawled: 2025-12-02T17:45:33Z
---

# quickLookPreview(_:in:)

**Instance Method**

Presents a Quick Look preview of the URLs you provide.

## Declaration

```swift
nonisolated func quickLookPreview<Items>(_ selection: Binding<Items.Element?>, in items: Items) -> some View where Items : RandomAccessCollection, Items.Element == URL

```

## Parameters

- **selection**: A [doc://com.apple.documentation/documentation/SwiftUI/Binding] to an element that’s part of the items collection. This is the URL that you currently want to preview.
- **items**: A collection of URLs to preview.

## Return Value

A view that presents the preview of the contents of the URL.

## Discussion

The Quick Look preview appears when you set the binding to a non-`nil` item. When you set the item back to `nil`, Quick Look dismisses the preview. If the value of the selection binding isn’t contained in the items collection, Quick Look treats it the same as a `nil` selection.

Quick Look updates the value of the selection binding to match the URL of the file the user is previewing. Upon dismissal by the user, Quick Look automatically sets the item binding to `nil`.

## Previewing content

- **quickLookPreview(_:)**: Presents a Quick Look preview of the contents of a single URL.

