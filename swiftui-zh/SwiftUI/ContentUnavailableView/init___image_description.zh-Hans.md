--- 来源：https://developer.apple.com/documentation/SwiftUI/ContentUnavailableView/init(_:image:description:)

抓取时间：2025-12-03T04:16:37Z

---

# init(_:image:description:)

**Initializer**

创建一个界面，该界面包含一个由本地化字符串生成的标题、一张图片和一些附加内容，用于在应用内容对用户不可用时显示。

## 声明

```swift
nonisolated init(_ title: LocalizedStringKey, image name: String, description: Text? = nil)
```

## 参数

- **title**：由本地化字符串生成的标题。

- **description**：描述该界面的视图。

## 创建不可用视图

- **init(label:description:actions:)**：创建一个包含标签和附加内容的界面，用于在应用内容对用户不可用时显示。

- **init(_:systemImage:description:)**：创建一个包含由本地化字符串生成的标题、系统图标图像和附加内容的界面，用于在应用内容对用户不可用时显示。


---
source: https://developer.apple.com/documentation/SwiftUI/ContentUnavailableView/init(_:image:description:)
crawled: 2025-12-03T04:16:37Z
---

# init(_:image:description:)

**Initializer**

Creates an interface, consisting of a title generated from a localized string, an image and additional content, that you display when the content of your app is unavailable to users.

## Declaration

```swift
nonisolated init(_ title: LocalizedStringKey, image name: String, description: Text? = nil)
```

## Parameters

- **title**: A title generated from a localized string.
- **description**: The view that describes the interface.

## Creating an unavailable view

- **init(label:description:actions:)**: Creates an interface, consisting of a label and additional content, that you display when the content of your app is unavailable to users.
- **init(_:systemImage:description:)**: Creates an interface, consisting of a title generated from a localized string, a system icon image and additional content, that you display when the content of your app is unavailable to users.

