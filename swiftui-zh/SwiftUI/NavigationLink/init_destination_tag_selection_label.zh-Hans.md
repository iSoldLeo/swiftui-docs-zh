---
来源: https://developer.apple.com/documentation/SwiftUI/NavigationLink/init(目的地:标签:选择:标签:)
抓取时间： 2025-12-03T17:20:53Z
---

# init(destination:tag:selection:label:)

**Initializer**

创建一个导航链接，当绑定的选择变量等于给定的标记值时，该链接会显示目标视图。

### 声明

```swift
init<V>(destination: Destination, tag: V, selection: Binding<V?>, @ViewBuilder label: () -> Label) where V : Hashable
```

## 参数

- **destination**：用于显示导航链接的视图。
- **tag**：使链接显示`selection`的`destination`值。
- **selection**：绑定变量，当 `selection` 等于 `tag` 时，该变量会导致链接显示 `destination`。
- **label**：视图生成器，用于生成描述`destination` 的标签。

## 使用视图参数创建链接

- **init(_:destination:isActive:)**：创建一个导航链接，该链接在激活时会显示一个目标视图，并带有一个由本地化字符串键生成的文本标签。
- **init(destination:isActive:label:)**：创建一个导航链接，在活动时显示目标视图。
- **init(_:destination:tag:selection:)**：创建一个导航链接，当绑定的选择变量与您提供的值相匹配时，该链接会使用从标题字符串生成的文本标签显示目标视图。


---
source: https://developer.apple.com/documentation/SwiftUI/NavigationLink/init(destination:tag:selection:label:)
crawled: 2025-12-03T17:20:53Z
---

# init(destination:tag:selection:label:)

**Initializer**

Creates a navigation link that presents the destination view when a bound selection variable equals a given tag value.

## Declaration

```swift
init<V>(destination: Destination, tag: V, selection: Binding<V?>, @ViewBuilder label: () -> Label) where V : Hashable
```

## Parameters

- **destination**: A view for the navigation link to present.
- **tag**: The value of `selection` that causes the link to present `destination`.
- **selection**: A bound variable that causes the link to present `destination` when `selection` becomes equal to `tag`.
- **label**: A view builder to produce a label describing the `destination` to present.

## Creating links with view arguments

- **init(_:destination:isActive:)**: Creates a navigation link that presents a destination view when active, with a text label that the link generates from a localized string key.
- **init(destination:isActive:label:)**: Creates a navigation link that presents the destination view when active.
- **init(_:destination:tag:selection:)**: Creates a navigation link that presents a destination view when a bound selection variable matches a value you provide, using a text label that the link generates from a title string.

