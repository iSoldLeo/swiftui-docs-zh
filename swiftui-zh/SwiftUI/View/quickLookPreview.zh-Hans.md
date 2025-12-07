--- 来源：https://developer.apple.com/documentation/SwiftUI/View/quickLookPreview(_:)

抓取时间：2025-12-02T17:45:32Z

---

# quickLookPreview(_:)

**实例方法**

快速预览单个 URL 的内容。

## 声明

```swift
nonisolated func quickLookPreview(_ item: Binding<URL?>) -> some View

```

## 参数

- **item**：要预览的 URL。

## 返回值

显示 URL 内容预览的视图。

## 说明

当您将绑定设置为非 `nil` 项时，将显示快速预览。当您将项目设置回 `nil` 时，“快速查看”功能会关闭预览。

用户关闭预览后，“快速查看”功能会自动将项目绑定设置为 `nil`。当设置的项目不是 `nil` 时，“快速查看”功能会显示预览。将 `item` 设置为 `nil` 即可关闭预览。

## 预览内容

- **quickLookPreview(_:in:)**：显示您提供的 URL 的“快速查看”预览。


---
source: https://developer.apple.com/documentation/SwiftUI/View/quickLookPreview(_:)
crawled: 2025-12-02T17:45:32Z
---

# quickLookPreview(_:)

**Instance Method**

Presents a Quick Look preview of the contents of a single URL.

## Declaration

```swift
nonisolated func quickLookPreview(_ item: Binding<URL?>) -> some View

```

## Parameters

- **item**: A [doc://com.apple.documentation/documentation/SwiftUI/Binding] to a URL that should be previewed.

## Return Value

A view that presents the preview of the contents of the URL.

## Discussion

The Quick Look preview appears when you set the binding to a non-`nil` item. When you set the item back to `nil`, Quick Look dismisses the preview.

Upon dismissal by the user, Quick Look automatically sets the item binding to `nil`. Quick Look displays the preview when a non-`nil` item is set. Set `item` to `nil` to dismiss the preview.

## Previewing content

- **quickLookPreview(_:in:)**: Presents a Quick Look preview of the URLs you provide.

