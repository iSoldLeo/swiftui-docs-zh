---
来源：https://developer.apple.com/documentation/SwiftUI/DocumentGroupLaunchScene/init(_:_:background:)
抓取时间：2025-12-01T10:48:05Z
---

# init(_:_:background:)

**Initializer**

为基于文档的应用程序创建一个启动场景，包含一个标题、一组操作和一个背景。

### 声明

```swift
nonisolated init(_ title: LocalizedStringKey, @ViewBuilder _ actions: () -> Actions, @ViewBuilder background: () -> some View)
```

## 参数

- **title**：用于视图标题的键。
- **actions**：用于返回视图操作的视图创建器。
- **background**：场景的背景。

## 讨论

请在[DocumentGroup](../DocumentGroup.zh-Hans.md) 场景旁使用`DocumentGroupLaunchScene`。如果您没有在应用程序声明中实施`DocumentGroup`，您可以通过实施[DocumentLaunchView](../DocumentLaunchView.zh-Hans.md)来获得相同的设计。


---
source: https://developer.apple.com/documentation/SwiftUI/DocumentGroupLaunchScene/init(_:_:background:)
crawled: 2025-12-01T10:48:05Z
---

# init(_:_:background:)

**Initializer**

Creates a launch scene for document-based applications with a title, a set of actions, and a background.

## Declaration

```swift
nonisolated init(_ title: LocalizedStringKey, @ViewBuilder _ actions: () -> Actions, @ViewBuilder background: () -> some View)
```

## Parameters

- **title**: A key to use for the view title.
- **actions**: A view builder for returning the view’s actions.
- **background**: The background of the scene.

## Discussion

Use a `DocumentGroupLaunchScene` alongside any [DocumentGroup](../DocumentGroup.zh-Hans.md) scenes. If you don’t implement a `DocumentGroup` in the app declaration, you can get the same design by implementing a [DocumentLaunchView](../DocumentLaunchView.zh-Hans.md).

