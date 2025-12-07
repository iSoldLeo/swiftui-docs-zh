---
来源：https://developer.apple.com/documentation/SwiftUI/NavigationLink/init(_:isActive:destination:)
抓取时间： 2025-12-03T17:20:45Z


# init(_:isActive:destination:)

**Initializer**

创建一个导航链接，该链接在激活时会显示一个目标视图，并带有一个由本地化字符串键生成的文本标签。

### 声明

```swift
nonisolated init(_ titleKey: LocalizedStringKey, isActive: Binding<Bool>, @ViewBuilder destination: () -> Destination)
```

## 参数

- **titleKey**：用于创建文本标签的本地化字符串键。
- **isActive**：与布尔值的绑定，表示当前是否显示`destination`。
- **destination**：用于显示导航链接的视图。

## 使用视图创建器创建链接

- **init(isActive:destination:label:)**：创建一个导航链接，在激活时显示目标视图。
- **init(_:tag:selection:destination:)**：**init(_:tag:selection:destination:)**： 创建导航链接，当绑定的选择变量与您提供的值相匹配时，该链接会使用从标题字符串生成的文本标签显示目标视图。
- **init(tag:selection:destination:label:)**：创建一个导航链接，当绑定的选择变量等于给定的标签值时显示目标视图。


---
source: https://developer.apple.com/documentation/SwiftUI/NavigationLink/init(_:isActive:destination:)
crawled: 2025-12-03T17:20:45Z
---

# init(_:isActive:destination:)

**Initializer**

Creates a navigation link that presents a destination view when active, with a text label that the link generates from a localized string key.

## Declaration

```swift
nonisolated init(_ titleKey: LocalizedStringKey, isActive: Binding<Bool>, @ViewBuilder destination: () -> Destination)
```

## Parameters

- **titleKey**: A localized string key for creating a text label.
- **isActive**: A binding to a Boolean value that indicates whether `destination` is currently presented.
- **destination**: A view for the navigation link to present.

## Creating links with view builders

- **init(isActive:destination:label:)**: Creates a navigation link that presents the destination view when active.
- **init(_:tag:selection:destination:)**: Creates a navigation link that presents a destination view when a bound selection variable matches a value you provide, using a text label that the link generates from a title string.
- **init(tag:selection:destination:label:)**: Creates a navigation link that presents the destination view when a bound selection variable equals a given tag value.

