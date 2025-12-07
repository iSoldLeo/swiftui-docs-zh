---
来源: https://developer.apple.com/documentation/SwiftUI/NavigationLink/init(_:destination:tag:selection:)
抓取时间： 2025-12-01T22:06:07Z
---

# init(_:destination:tag:selection:)

**Initializer**

创建一个导航链接，当绑定的选择变量与您提供的值相匹配时，该链接就会显示目标视图，并使用由标题字符串生成的文本标签。

### 声明

```swift
nonisolated init<S, V>(_ title: S, destination: Destination, tag: V, selection: Binding<V?>) where S : StringProtocol, V : Hashable
```

## 参数

- **title**：用于创建文本标签的字符串。
- **destination**：用于显示导航链接的视图。
- **tag**：使链接显示`selection`的`destination`值。
- **selection**：绑定变量，当 `selection` 等于 `tag` 时，该变量会导致链接显示 `destination`。

## 使用视图参数创建链接

- **init(_:destination:isActive:)**：创建一个导航链接，该链接在激活时会显示一个目标视图，并带有由本地化字符串键生成的文本标签。
- **init(destination:isActive:label:)**：创建一个导航链接，在活动时显示目标视图。
- **init(destination:tag:selection:label:)**：创建导航链接，当绑定的选择变量等于给定的标记值时显示目标视图。


---
source: https://developer.apple.com/documentation/SwiftUI/NavigationLink/init(_:destination:tag:selection:)
crawled: 2025-12-01T22:06:07Z
---

# init(_:destination:tag:selection:)

**Initializer**

Creates a navigation link that presents a destination view when a bound selection variable matches a value you provide, using a text label that the link generates from a title string.

## Declaration

```swift
nonisolated init<S, V>(_ title: S, destination: Destination, tag: V, selection: Binding<V?>) where S : StringProtocol, V : Hashable
```

## Parameters

- **title**: A string for creating a text label.
- **destination**: A view for the navigation link to present.
- **tag**: The value of `selection` that causes the link to present `destination`.
- **selection**: A bound variable that causes the link to present `destination` when `selection` becomes equal to `tag`.

## Creating links with view arguments

- **init(_:destination:isActive:)**: Creates a navigation link that presents a destination view when active, with a text label that the link generates from a localized string key.
- **init(destination:isActive:label:)**: Creates a navigation link that presents the destination view when active.
- **init(destination:tag:selection:label:)**: Creates a navigation link that presents the destination view when a bound selection variable equals a given tag value.

