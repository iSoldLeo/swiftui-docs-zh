---
来源：https://developer.apple.com/documentation/SwiftUI/NavigationLink/init(目的地：标签：)
抓取时间： 2025-12-01T00:42:48Z
---

# init(destination:label:)

**Initializer**

创建导航链接，显示目的地视图。

## 声明

```swift
init(@ViewBuilder destination: () -> Destination, @ViewBuilder label: () -> Label)
```

## 参数

- **destination**：用于显示导航链接的视图。
- **label**：视图生成器，用于生成描述`destination` 的标签。

## 呈现目标视图

- **init(_:destination:)**：创建一个导航链接，显示目的地视图，并带有由本地化字符串键生成的文本标签。


---
source: https://developer.apple.com/documentation/SwiftUI/NavigationLink/init(destination:label:)
crawled: 2025-12-01T00:42:48Z
---

# init(destination:label:)

**Initializer**

Creates a navigation link that presents the destination view.

## Declaration

```swift
init(@ViewBuilder destination: () -> Destination, @ViewBuilder label: () -> Label)
```

## Parameters

- **destination**: A view for the navigation link to present.
- **label**: A view builder to produce a label describing the `destination` to present.

## Presenting a destination view

- **init(_:destination:)**: Creates a navigation link that presents a destination view, with a text label that the link generates from a localized string key.

