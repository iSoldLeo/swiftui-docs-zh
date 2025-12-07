--- 来源：https://developer.apple.com/documentation/SwiftUI/View/accessibilityShowsLargeContentViewer(_:)

抓取时间：2025-11-30T21:28:37Z

---

# accessibilityShowsLargeContentViewer(_:)

**实例方法**

添加一个自定义的大内容视图，供大内容查看器显示。

## 声明

```swift
nonisolated func accessibilityShowsLargeContentViewer<V>(@ViewBuilder _ largeContentView: () -> V) -> some View where V : View

```

## 讨论

仅在由于不可避免的设计限制，某些项目必须保持较小尺寸的情况下才使用大内容查看器。例如，标签栏中的按钮保持较小尺寸，以便为应用程序的主要内容留出更多空间。

以下示例展示了如何添加自定义的大内容视图：

```swift
var body: some View {
    Button(action: newMessage) {
        Image(systemName: "plus")
    }
    .accessibilityShowsLargeContentViewer {
        Label("New Message", systemImage: "plus")
    }
}
```

请勿使用大内容查看器来替代正确的动态类型支持。例如，动态类型允许列表中的项目垂直放大或缩小，以适应用户偏好的字体大小。仅当由于不可避免的设计限制，项目必须保持较小尺寸时，才应使用大内容查看器。

例如，动态类型大小受 [dynamicTypeSize(_:)](dynamicTypeSize.zh-Hans.md) 限制的视图可能需要大内容视图。

## 放大内容

- **accessibilityShowsLargeContentViewer()**：添加一个默认的大内容视图，供大内容查看器显示。

- **accessibilityLargeContentViewerEnabled**：是否启用大内容查看器。


---
source: https://developer.apple.com/documentation/SwiftUI/View/accessibilityShowsLargeContentViewer(_:)
crawled: 2025-11-30T21:28:37Z
---

# accessibilityShowsLargeContentViewer(_:)

**Instance Method**

Adds a custom large content view to be shown by the large content viewer.

## Declaration

```swift
nonisolated func accessibilityShowsLargeContentViewer<V>(@ViewBuilder _ largeContentView: () -> V) -> some View where V : View

```

## Discussion

Rely on the large content viewer only in situations where items must remain small due to unavoidable design constraints. For example, buttons in a tab bar remain small to leave more room for the main app content.

The following example shows how to add a custom large content view:

```swift
var body: some View {
    Button(action: newMessage) {
        Image(systemName: "plus")
    }
    .accessibilityShowsLargeContentViewer {
        Label("New Message", systemImage: "plus")
    }
}
```

Don’t use the large content viewer as a replacement for proper Dynamic Type support. For example, Dynamic Type allows items in a list to grow or shrink vertically to accommodate the user’s preferred font size. Rely on the large content viewer only in situations where items must remain small due to unavoidable design constraints.

For example, views that have their Dynamic Type size constrained with [dynamicTypeSize(_:)](dynamicTypeSize.zh-Hans.md) may require a large content view.

## Enlarging content

- **accessibilityShowsLargeContentViewer()**: Adds a default large content view to be shown by the large content viewer.
- **accessibilityLargeContentViewerEnabled**: Whether the Large Content Viewer is enabled.

