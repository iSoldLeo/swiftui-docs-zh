--- 来源：https://developer.apple.com/documentation/SwiftUI/ContentUnavailableView/init(label:description:actions:)

抓取时间：2025-12-03T04:16:36Z

---

# init(label:description:actions:)

**Initializer**

创建一个界面，包含一个标签和一些附加内容，用于在应用内容对用户不可用时显示。

## 声明

```swift
init(@ViewBuilder label: () -> Label, @ViewBuilder description: () -> Description = { EmptyView() }, @ViewBuilder actions: () -> Actions = { EmptyView() })
```

## 参数

- **label**：描述视图的标签。

- **description**：描述界面的视图。

- **actions**：界面操作的内容。

## 创建不可用视图

- **init(_:image:description:)**：创建一个界面，包含由本地化字符串生成的标题、图像和其他内容，用于在您的应用内容对用户不可用时显示。

- **init(_:systemImage:description:)**：创建一个界面，包含由本地化字符串生成的标题、系统图标图像和其他内容，用于在您的应用内容对用户不可用时显示。


---
source: https://developer.apple.com/documentation/SwiftUI/ContentUnavailableView/init(label:description:actions:)
crawled: 2025-12-03T04:16:36Z
---

# init(label:description:actions:)

**Initializer**

Creates an interface, consisting of a label and additional content, that you display when the content of your app is unavailable to users.

## Declaration

```swift
init(@ViewBuilder label: () -> Label, @ViewBuilder description: () -> Description = { EmptyView() }, @ViewBuilder actions: () -> Actions = { EmptyView() })
```

## Parameters

- **label**: The label that describes the view.
- **description**: The view that describes the interface.
- **actions**: The content of the interface actions.

## Creating an unavailable view

- **init(_:image:description:)**: Creates an interface, consisting of a title generated from a localized string, an image and additional content, that you display when the content of your app is unavailable to users.
- **init(_:systemImage:description:)**: Creates an interface, consisting of a title generated from a localized string, a system icon image and additional content, that you display when the content of your app is unavailable to users.

