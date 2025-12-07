---
来源： https://developer.apple.com/documentation/SwiftUI/Visibility/visible
抓取时间： 2025-12-03T06:08:28Z
---

# Visibility.visible

**Case**

元素可能可见。

## 声明

```swift
case visible
```

## 讨论

某些 API 可能会使用此值来表示提示或偏好，而不是强制断言。例如，使用[listRowSeparator(_:edges:)](../View/listRowSeparator___edges.zh-Hans.md)修饰符将列表行分隔符可见性设置为`visible`，可能并不总能产生任何可见的分隔符，特别是对于设计中不包含分隔符的列表样式。

## 获取可见性选项

- **Visibility.automatic**：根据接受可见性配置的组件的策略，元素可能可见或隐藏。
- **Visibility.hidden**：该元素可能被隐藏。


---
source: https://developer.apple.com/documentation/SwiftUI/Visibility/visible
crawled: 2025-12-03T06:08:28Z
---

# Visibility.visible

**Case**

The element may be visible.

## Declaration

```swift
case visible
```

## Discussion

Some APIs may use this value to represent a hint or preference, rather than a mandatory assertion. For example, setting list row separator visibility to `visible` using the [listRowSeparator(_:edges:)](../View/listRowSeparator___edges.zh-Hans.md) modifier may not always result in any visible separators, especially for list styles that do not include separators as part of their design.

## Getting visibility options

- **Visibility.automatic**: The element may be visible or hidden depending on the policies of the component accepting the visibility configuration.
- **Visibility.hidden**: The element may be hidden.

