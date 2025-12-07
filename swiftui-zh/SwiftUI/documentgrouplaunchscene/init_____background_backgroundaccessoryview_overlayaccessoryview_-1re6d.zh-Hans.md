---
來源: https://developer.apple.com/documentation/swiftui/documentgrouplaunchscene/init(_:_:background:backgroundaccessoryview:overlayaccessoryview:)-1re6d
抓取时间：2025-11-30T21:14:07Z
---

# init(_:_:background:backgroundAccessoryView:overlayAccessoryView:)

**Initializer**

为基于文档的应用程序创建具有标题、操作集和背景的启动场景。

### 声明

```swift
nonisolated init(_ title: LocalizedStringKey, @ViewBuilder _ actions: () -> Actions, @ViewBuilder background: () -> some View, @ViewBuilder backgroundAccessoryView: @escaping (DocumentLaunchGeometryProxy) -> some View, @ViewBuilder overlayAccessoryView: @escaping (DocumentLaunchGeometryProxy) -> some View)
```

## 参数

- **title**：用于视图标题的键。
- **actions**：用于返回视图操作的视图生成器。
- **background**：场景的背景。
- **backgroundAccessoryView**：场景的背景：用于返回视图背景附属视图的视图生成器。
- **overlayAccessoryView**：用于返回视图叠加附件视图的视图创建器。

## 讨论

在使用任何[DocumentGroup](../DocumentGroup.zh-Hans.md) 场景的同时使用`DocumentGroupLaunchScene`。如果您没有在应用程序声明中实施`DocumentGroup`，您可以通过实施[DocumentLaunchView](../DocumentLaunchView.zh-Hans.md)获得相同的设计。


---
source: https://developer.apple.com/documentation/swiftui/documentgrouplaunchscene/init(_:_:background:backgroundaccessoryview:overlayaccessoryview:)-1re6d
crawled: 2025-11-30T21:14:07Z
---

# init(_:_:background:backgroundAccessoryView:overlayAccessoryView:)

**Initializer**

Creates a launch scene for document-based applications with a title, a set of actions, and a background.

## Declaration

```swift
nonisolated init(_ title: LocalizedStringKey, @ViewBuilder _ actions: () -> Actions, @ViewBuilder background: () -> some View, @ViewBuilder backgroundAccessoryView: @escaping (DocumentLaunchGeometryProxy) -> some View, @ViewBuilder overlayAccessoryView: @escaping (DocumentLaunchGeometryProxy) -> some View)
```

## Parameters

- **title**: A key to use for the view title.
- **actions**: A view builder for returning the view’s actions.
- **background**: The background of the scene.
- **backgroundAccessoryView**: A view builder for returning the view’s background accessory view.
- **overlayAccessoryView**: A view builder for returning the view’s overlay accessory view.

## Discussion

Use a `DocumentGroupLaunchScene` alongside any [DocumentGroup](../DocumentGroup.zh-Hans.md) scenes. If you don’t implement a `DocumentGroup` in the app declaration, you can get the same design by implementing a [DocumentLaunchView](../DocumentLaunchView.zh-Hans.md).

