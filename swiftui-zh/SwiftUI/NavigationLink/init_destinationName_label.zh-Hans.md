---
来源：https://developer.apple.com/documentation/SwiftUI/NavigationLink/init(目的地名称：标签：)
抓取时间：2025-12-01T22:06:05Z
---

# init(destinationName:label:)

**Initializer**

创建导航链接，从 WatchKit 故事板显示视图。

## 声明

```swift
nonisolated init(destinationName: String, @ViewBuilder label: () -> Label)
```

## 参数

- **destinationName**：要显示导航链接的视图的故事板名称。
- **label**：视图生成器，用于生成描述要显示的`destination` 的标签。

## 为 WatchKit 创建链接

- **init(destinationName:isActive:label:)**：创建一个导航链接，激活后可显示 WatchKit 故事板中的视图。
- **init(destinationName:tag:selection:label:)**：创建一个导航链接，当绑定的选择变量与您提供的值匹配时，该链接将显示 WatchKit 故事板中的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/NavigationLink/init(destinationName:label:)
crawled: 2025-12-01T22:06:05Z
---

# init(destinationName:label:)

**Initializer**

Creates a navigation link that presents a view from a WatchKit storyboard.

## Declaration

```swift
nonisolated init(destinationName: String, @ViewBuilder label: () -> Label)
```

## Parameters

- **destinationName**: The storyboard name of a view for the navigation link to present.
- **label**: A view builder to produce a label describing the `destination` to present.

## Creating links for WatchKit

- **init(destinationName:isActive:label:)**: Creates a navigation link that presents a view from a WatchKit storyboard when active.
- **init(destinationName:tag:selection:label:)**: Creates a navigation link that presents a view from a WatchKit storyboard when a bound selection variable matches a value you provide.

