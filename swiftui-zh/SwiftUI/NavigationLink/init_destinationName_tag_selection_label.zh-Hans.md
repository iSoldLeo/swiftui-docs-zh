---
来源： https://developer.apple.com/documentation/SwiftUI/NavigationLink/init(destinationName:tag:selection:label:)
抓取时间：2025-12-01T22:06:05Z
---

# init(destinationName:tag:selection:label:)

**Initializer**

创建一个导航链接，当绑定的选择变量与您提供的值匹配时，该链接将显示 WatchKit 故事板中的视图。

## 声明

```swift
nonisolated init<V>(destinationName: String, tag: V, selection: Binding<V?>, @ViewBuilder label: () -> Label) where V : Hashable
```

## 参数

- **destinationName**：要显示导航链接的视图的故事板名称。
- **tag**：使链接显示`selection`的`destination`值。
- **selection**：绑定变量，当 `selection` 等于 `tag` 时，该变量会导致链接显示 `destination`。
- **label**：视图生成器，用于生成描述`destination` 的标签。

## 为 WatchKit 创建链接

- **init(destinationName:isActive:label:)**：创建一个导航链接，激活后可显示 WatchKit 故事板中的视图。
- **init(destinationName:label:)**：创建可显示 WatchKit 故事板视图的导航链接。


---
source: https://developer.apple.com/documentation/SwiftUI/NavigationLink/init(destinationName:tag:selection:label:)
crawled: 2025-12-01T22:06:05Z
---

# init(destinationName:tag:selection:label:)

**Initializer**

Creates a navigation link that presents a view from a WatchKit storyboard when a bound selection variable matches a value you provide.

## Declaration

```swift
nonisolated init<V>(destinationName: String, tag: V, selection: Binding<V?>, @ViewBuilder label: () -> Label) where V : Hashable
```

## Parameters

- **destinationName**: The storyboard name of a view for the navigation link to present.
- **tag**: The value of `selection` that causes the link to present `destination`.
- **selection**: A bound variable that causes the link to present `destination` when `selection` becomes equal to `tag`.
- **label**: A view builder to produce a label describing the `destination` to present.

## Creating links for WatchKit

- **init(destinationName:isActive:label:)**: Creates a navigation link that presents a view from a WatchKit storyboard when active.
- **init(destinationName:label:)**: Creates a navigation link that presents a view from a WatchKit storyboard.

