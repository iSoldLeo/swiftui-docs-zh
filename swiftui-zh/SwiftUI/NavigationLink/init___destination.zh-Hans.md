---
来源： https://developer.apple.com/documentation/SwiftUI/NavigationLink/init(_:destination:)
抓取时间：2025-12-02T20:58:42Z
---

# init(_:destination:)

**Initializer**

创建一个导航链接，显示一个目的地视图，并带有该链接根据本地化字符串键生成的文本标签。

### 声明

```swift
nonisolated init(_ titleKey: LocalizedStringKey, @ViewBuilder destination: () -> Destination)
```

## 参数

- **titleKey**：用于创建文本标签的本地化字符串键。
- **destination**：用于显示导航链接的视图。

## 呈现目的地视图

- **init(destination:label:)**：创建一个导航链接，用于显示目标视图。


---
source: https://developer.apple.com/documentation/SwiftUI/NavigationLink/init(_:destination:)
crawled: 2025-12-02T20:58:42Z
---

# init(_:destination:)

**Initializer**

Creates a navigation link that presents a destination view, with a text label that the link generates from a localized string key.

## Declaration

```swift
nonisolated init(_ titleKey: LocalizedStringKey, @ViewBuilder destination: () -> Destination)
```

## Parameters

- **titleKey**: A localized string key for creating a text label.
- **destination**: A view for the navigation link to present.

## Presenting a destination view

- **init(destination:label:)**: Creates a navigation link that presents the destination view.

