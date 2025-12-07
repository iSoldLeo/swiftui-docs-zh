---
来源：https://developer.apple.com/documentation/SwiftUI/DocumentGroupLaunchScene/init(_:backgroundStyle:_:)
抓取时间： 2025-12-03T05:59:10Z
---

# init(_:backgroundStyle:_:)

**Initializer**

为基于文档的应用程序创建一个启动场景，该场景包含一个标题、一种背景样式和一组操作。

### 声明

```swift
nonisolated init<B>(_ title: LocalizedStringKey, backgroundStyle: B = BackgroundStyle(), @ViewBuilder _ actions: () -> Actions = { DefaultDocumentGroupLaunchActions() }) where B : ShapeStyle
```

## 参数

- **title**：用于视图标题的键。
- **backgroundStyle**：视图的背景样式。
- **actions**：视图的背景样式：用于返回视图操作的视图创建器。

## 讨论

在使用任何[DocumentGroup](../DocumentGroup.zh-Hans.md) 场景的同时使用`DocumentGroupLaunchScene`。如果您没有在应用程序声明中实施`DocumentGroup`，您可以通过实施[DocumentLaunchView](../DocumentLaunchView.zh-Hans.md)来获得相同的设计。


---
source: https://developer.apple.com/documentation/SwiftUI/DocumentGroupLaunchScene/init(_:backgroundStyle:_:)
crawled: 2025-12-03T05:59:10Z
---

# init(_:backgroundStyle:_:)

**Initializer**

Creates a launch scene for document-based applications with a title, a background style, and a set of actions.

## Declaration

```swift
nonisolated init<B>(_ title: LocalizedStringKey, backgroundStyle: B = BackgroundStyle(), @ViewBuilder _ actions: () -> Actions = { DefaultDocumentGroupLaunchActions() }) where B : ShapeStyle
```

## Parameters

- **title**: A key to use for the view title.
- **backgroundStyle**: A background style of the view.
- **actions**: A view builder for returning the view’s actions.

## Discussion

Use a `DocumentGroupLaunchScene` alongside any [DocumentGroup](../DocumentGroup.zh-Hans.md) scenes. If you don’t implement a `DocumentGroup` in the app declaration, you can get the same design by implementing a [DocumentLaunchView](../DocumentLaunchView.zh-Hans.md).

