---
source: https://developer.apple.com/documentation/SwiftUI/NavigationLink/init(_:destination:isActive:)
抓取时间： 2025-12-01T22:06:06Z


# init(_:destination:isActive:)

**Initializer**

创建一个导航链接，在活动时显示目的地视图，并带有一个文本标签，该标签由链接通过本地化字符串键生成。

### 声明

```swift
nonisolated init(_ titleKey: LocalizedStringKey, destination: Destination, isActive: Binding<Bool>)
```

## 参数

- **titleKey**：用于创建文本标签的本地化字符串键。
- **destination**：用于显示导航链接的视图。
- **isActive**：与布尔值的绑定，表示当前是否显示`destination`。

## 使用视图参数创建链接

- **init(destination:isActive:label:)**：创建一个导航链接，在活动时显示目标视图。
- **init(_:destination:tag:selection:)**：**init(_:destination:tag:selection:)**： 创建导航链接，当绑定的选择变量与您提供的值相匹配时，该链接会使用从标题字符串生成的文本标签显示目标视图。
- **init(destination:tag:selection:label:)**：创建一个导航链接，当绑定的选择变量等于给定的标签值时显示目标视图。


---
source: https://developer.apple.com/documentation/SwiftUI/NavigationLink/init(_:destination:isActive:)
crawled: 2025-12-01T22:06:06Z
---

# init(_:destination:isActive:)

**Initializer**

Creates a navigation link that presents a destination view when active, with a text label that the link generates from a localized string key.

## Declaration

```swift
nonisolated init(_ titleKey: LocalizedStringKey, destination: Destination, isActive: Binding<Bool>)
```

## Parameters

- **titleKey**: A localized string key for creating a text label.
- **destination**: A view for the navigation link to present.
- **isActive**: A binding to a Boolean value that indicates whether `destination` is currently presented.

## Creating links with view arguments

- **init(destination:isActive:label:)**: Creates a navigation link that presents the destination view when active.
- **init(_:destination:tag:selection:)**: Creates a navigation link that presents a destination view when a bound selection variable matches a value you provide, using a text label that the link generates from a title string.
- **init(destination:tag:selection:label:)**: Creates a navigation link that presents the destination view when a bound selection variable equals a given tag value.

