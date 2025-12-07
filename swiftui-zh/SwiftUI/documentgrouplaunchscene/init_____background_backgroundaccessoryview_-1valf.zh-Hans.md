---
來源: https://developer.apple.com/documentation/swiftui/documentgrouplaunchscene/init(_:_:background:backgroundaccessoryview:)-1valf
抓取时间：2025-12-02T17:29:02Z
---

# init(_:_:background:backgroundAccessoryView:)

**Initializer**

为基于文档的应用程序创建一个启动场景，该场景包含一个标题、一组操作、一个背景和一个背景配件视图。

## 声明

```swift
nonisolated init(_ title: LocalizedStringKey, @ViewBuilder _ actions: () -> Actions, @ViewBuilder background: () -> some View, @ViewBuilder backgroundAccessoryView: @escaping (DocumentLaunchGeometryProxy) -> some View)
```

## 参数

- **title**：用于视图标题的键。
- **actions**：用于返回视图操作的视图创建器。
- **background**：场景的背景。
- **backgroundAccessoryView**：场景的背景：用于返回视图背景附属视图的视图生成器。

## 讨论

在使用任何[DocumentGroup](../DocumentGroup.zh-Hans.md) 场景的同时使用`DocumentGroupLaunchScene`。如果您没有在应用程序声明中实施`DocumentGroup`，您可以通过实施[DocumentLaunchView](../DocumentLaunchView.zh-Hans.md)获得相同的设计。


---
source: https://developer.apple.com/documentation/swiftui/documentgrouplaunchscene/init(_:_:background:backgroundaccessoryview:)-1valf
crawled: 2025-12-02T17:29:02Z
---

# init(_:_:background:backgroundAccessoryView:)

**Initializer**

Creates a launch scene for document-based applications with a title, a set of actions, a background, and a background accessory view.

## Declaration

```swift
nonisolated init(_ title: LocalizedStringKey, @ViewBuilder _ actions: () -> Actions, @ViewBuilder background: () -> some View, @ViewBuilder backgroundAccessoryView: @escaping (DocumentLaunchGeometryProxy) -> some View)
```

## Parameters

- **title**: A key to use for the view title.
- **actions**: A view builder for returning the view’s actions.
- **background**: The background of the scene.
- **backgroundAccessoryView**: A view builder for returning the view’s background accessory view.

## Discussion

Use a `DocumentGroupLaunchScene` alongside any [DocumentGroup](../DocumentGroup.zh-Hans.md) scenes. If you don’t implement a `DocumentGroup` in the app declaration, you can get the same design by implementing a [DocumentLaunchView](../DocumentLaunchView.zh-Hans.md).

