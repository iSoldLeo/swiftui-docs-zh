---
source: https://developer.apple.com/documentation/SwiftUI/NavigationLink/init(destination:isActive:label:)
抓取时间： 2025-12-03T17:20:51Z
---

# init(destination:isActive:label:)

**Initializer**

创建一个导航链接，在目标视图处于活动状态时显示该链接。

### 声明

```swift
init(destination: Destination, isActive: Binding<Bool>, @ViewBuilder label: () -> Label)
```

## 参数

- **destination**：用于显示导航链接的视图。
- **isActive**：与布尔值的绑定，表示当前是否显示`destination`。
- **label**：视图生成器，用于生成描述要显示的`destination` 的标签。

## 使用视图参数创建链接

- **init(_:destination:isActive:)**：创建一个导航链接，该链接在激活时会显示一个目标视图，并带有一个由本地化字符串键生成的文本标签。
- **init(_:destination:tag:selection:)**：创建一个导航链接，当绑定的选择变量与您提供的值相匹配时，该链接会显示目标视图，并使用由标题字符串生成的文本标签。
- **init(destination:tag:selection:label:)**：创建一个导航链接，当绑定的选择变量等于给定的标签值时显示目标视图。


---
source: https://developer.apple.com/documentation/SwiftUI/NavigationLink/init(destination:isActive:label:)
crawled: 2025-12-03T17:20:51Z
---

# init(destination:isActive:label:)

**Initializer**

Creates a navigation link that presents the destination view when active.

## Declaration

```swift
init(destination: Destination, isActive: Binding<Bool>, @ViewBuilder label: () -> Label)
```

## Parameters

- **destination**: A view for the navigation link to present.
- **isActive**: A binding to a Boolean value that indicates whether `destination` is currently presented.
- **label**: A view builder to produce a label describing the `destination` to present.

## Creating links with view arguments

- **init(_:destination:isActive:)**: Creates a navigation link that presents a destination view when active, with a text label that the link generates from a localized string key.
- **init(_:destination:tag:selection:)**: Creates a navigation link that presents a destination view when a bound selection variable matches a value you provide, using a text label that the link generates from a title string.
- **init(destination:tag:selection:label:)**: Creates a navigation link that presents the destination view when a bound selection variable equals a given tag value.

