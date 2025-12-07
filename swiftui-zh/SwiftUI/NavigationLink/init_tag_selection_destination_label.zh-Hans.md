---
来源：https://developer.apple.com/documentation/SwiftUI/NavigationLink/init(标签:选择:目的地:标签:)
抓取时间： 2025-12-01T22:06:03Z
---

# init(tag:selection:destination:label:)

**Initializer**

创建一个导航链接，当绑定的选择变量等于给定的标记值时，该链接会显示目标视图。

### 声明

```swift
init<V>(tag: V, selection: Binding<V?>, @ViewBuilder destination: () -> Destination, @ViewBuilder label: () -> Label) where V : Hashable
```

## 参数

- **tag**：`selection` 的值，该值会导致链接出现 `destination`。
- **selection**：绑定变量，当 `selection` 等于 `tag` 时，该变量会导致链接显示 `destination`。
- **destination**：用于显示导航链接的视图。
- **label**：视图生成器，用于生成描述要显示的`destination` 的标签。

## 使用视图创建器创建链接

- **init(_:isActive:destination:)**：创建一个导航链接，该链接在激活时会显示一个目标视图，并带有由本地化字符串键生成的文本标签。
- **init(isActive:destination:label:)**：创建一个导航链接，在活动时显示目标视图。
- **init(_:tag:selection:destination:)**：创建一个导航链接，当绑定的选择变量与您提供的值相匹配时，该链接会使用从标题字符串生成的文本标签显示目标视图。


---
source: https://developer.apple.com/documentation/SwiftUI/NavigationLink/init(tag:selection:destination:label:)
crawled: 2025-12-01T22:06:03Z
---

# init(tag:selection:destination:label:)

**Initializer**

Creates a navigation link that presents the destination view when a bound selection variable equals a given tag value.

## Declaration

```swift
init<V>(tag: V, selection: Binding<V?>, @ViewBuilder destination: () -> Destination, @ViewBuilder label: () -> Label) where V : Hashable
```

## Parameters

- **tag**: The value of `selection` that causes the link to present `destination`.
- **selection**: A bound variable that causes the link to present `destination` when `selection` becomes equal to `tag`.
- **destination**: A view for the navigation link to present.
- **label**: A view builder to produce a label describing the `destination` to present.

## Creating links with view builders

- **init(_:isActive:destination:)**: Creates a navigation link that presents a destination view when active, with a text label that the link generates from a localized string key.
- **init(isActive:destination:label:)**: Creates a navigation link that presents the destination view when active.
- **init(_:tag:selection:destination:)**: Creates a navigation link that presents a destination view when a bound selection variable matches a value you provide, using a text label that the link generates from a title string.

