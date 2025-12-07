---
来源：https://developer.apple.com/documentation/SwiftUI/DocumentGroupLaunchScene/init(_:_:background:overlayAccessoryView:)
抓取时间：2025-12-01T10:48:07Z
---

# init(_:_:background:overlayAccessoryView:)

**Initializer**

为基于文档的应用程序创建一个启动场景，该场景包含一个标题、一组操作、一个背景和一个覆盖附件视图。

### 声明

```swift
nonisolated init(_ title: LocalizedStringKey, @ViewBuilder _ actions: () -> Actions, @ViewBuilder background: () -> some View, @ViewBuilder overlayAccessoryView: @escaping (DocumentLaunchGeometryProxy) -> some View)
```

## 参数

- **title**：用于视图标题的键。
- **actions**：用于返回视图操作的视图创建器。
- **background**：场景的背景。
- **overlayAccessoryView**：场景的背景：用于返回视图叠加附件视图的视图生成器。

## 讨论

在使用任何[DocumentGroup](../DocumentGroup.zh-Hans.md) 场景的同时使用`DocumentGroupLaunchScene`。如果您没有在应用程序声明中实施`DocumentGroup`，您可以通过实施[DocumentLaunchView](../DocumentLaunchView.zh-Hans.md)获得相同的设计。


---
source: https://developer.apple.com/documentation/SwiftUI/DocumentGroupLaunchScene/init(_:_:background:overlayAccessoryView:)
crawled: 2025-12-01T10:48:07Z
---

# init(_:_:background:overlayAccessoryView:)

**Initializer**

Creates a launch scene for document-based applications with a title, a set of actions, a background, and an overlay accessory view.

## Declaration

```swift
nonisolated init(_ title: LocalizedStringKey, @ViewBuilder _ actions: () -> Actions, @ViewBuilder background: () -> some View, @ViewBuilder overlayAccessoryView: @escaping (DocumentLaunchGeometryProxy) -> some View)
```

## Parameters

- **title**: A key to use for the view title.
- **actions**: A view builder for returning the view’s actions.
- **background**: The background of the scene.
- **overlayAccessoryView**: A view builder for returning the view’s overlay accessory view.

## Discussion

Use a `DocumentGroupLaunchScene` alongside any [DocumentGroup](../DocumentGroup.zh-Hans.md) scenes. If you don’t implement a `DocumentGroup` in the app declaration, you can get the same design by implementing a [DocumentLaunchView](../DocumentLaunchView.zh-Hans.md).

