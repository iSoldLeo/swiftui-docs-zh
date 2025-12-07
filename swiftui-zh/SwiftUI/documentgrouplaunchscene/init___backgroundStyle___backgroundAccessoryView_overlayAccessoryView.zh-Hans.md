---
来源：https://developer.apple.com/documentation/SwiftUI/DocumentGroupLaunchScene/init(_:backgroundStyle:_:backgroundAccessoryView:overlayAccessoryView:)
抓取时间：2025-12-03T05:59:12Z
---

# init(_:backgroundStyle:_:backgroundAccessoryView:overlayAccessoryView:)

**Initializer**

为基于文档的应用程序创建一个启动场景，该场景包含一个标题、一种背景样式、一组操作以及背景和叠加附件视图。

### 声明

```swift
nonisolated init<B>(_ title: LocalizedStringKey, backgroundStyle: B = BackgroundStyle(), @ViewBuilder _ actions: () -> Actions = { DefaultDocumentGroupLaunchActions() }, @ViewBuilder backgroundAccessoryView: @escaping (DocumentLaunchGeometryProxy) -> some View, @ViewBuilder overlayAccessoryView: @escaping (DocumentLaunchGeometryProxy) -> some View) where B : ShapeStyle
```

## 参数

- **title**：用于视图标题的键。
- **backgroundStyle**：视图的背景样式。
- **actions**：视图的背景样式：用于返回视图操作的视图创建器。
- **backgroundAccessoryView**：用于返回视图动作的视图创建器：用于返回视图背景配件视图的视图创建器。
- **overlayAccessoryView**：用于返回视图叠加附件视图的视图创建器。

## 讨论

在使用任何[DocumentGroup](../DocumentGroup.zh-Hans.md) 场景的同时使用`DocumentGroupLaunchScene`。如果您没有在应用程序声明中实施`DocumentGroup`，您可以通过实施[DocumentLaunchView](../DocumentLaunchView.zh-Hans.md)获得相同的设计。


---
source: https://developer.apple.com/documentation/SwiftUI/DocumentGroupLaunchScene/init(_:backgroundStyle:_:backgroundAccessoryView:overlayAccessoryView:)
crawled: 2025-12-03T05:59:12Z
---

# init(_:backgroundStyle:_:backgroundAccessoryView:overlayAccessoryView:)

**Initializer**

Creates a launch scene for document-based applications with a title, a background style, a set of actions, and background and overlay accessory views.

## Declaration

```swift
nonisolated init<B>(_ title: LocalizedStringKey, backgroundStyle: B = BackgroundStyle(), @ViewBuilder _ actions: () -> Actions = { DefaultDocumentGroupLaunchActions() }, @ViewBuilder backgroundAccessoryView: @escaping (DocumentLaunchGeometryProxy) -> some View, @ViewBuilder overlayAccessoryView: @escaping (DocumentLaunchGeometryProxy) -> some View) where B : ShapeStyle
```

## Parameters

- **title**: A key to use for the view title.
- **backgroundStyle**: A background style of the view.
- **actions**: A view builder for returning the view’s actions.
- **backgroundAccessoryView**: A view builder for returning the view’s background accessory view.
- **overlayAccessoryView**: A view builder for returning the view’s overlay accessory view.

## Discussion

Use a `DocumentGroupLaunchScene` alongside any [DocumentGroup](../DocumentGroup.zh-Hans.md) scenes. If you don’t implement a `DocumentGroup` in the app declaration, you can get the same design by implementing a [DocumentLaunchView](../DocumentLaunchView.zh-Hans.md).

