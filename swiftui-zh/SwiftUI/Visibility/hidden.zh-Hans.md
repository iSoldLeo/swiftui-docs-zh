---
来源： https://developer.apple.com/documentation/SwiftUI/Visibility/hidden
抓取时间： 2025-12-03T06:08:29Z
---

# Visibility.hidden

**Case**

元素可能被隐藏。

## 声明

```swift
case hidden
```

## 讨论

某些 API 可能使用此值来表示提示或偏好，而不是强制断言。例如，使用 [confirmationDialog(_:isPresented:titleVisibility:actions:)](../View/confirmationDialog___isPresented_titleVisibility_actions.zh-Hans.md) 修改器将确认对话框标题可见性设置为 `hidden`，可能并不总是隐藏对话框标题，而这在某些平台上是必需的。

## 获取可见性选项

- **Visibility.automatic**：根据接受可见性配置的组件的策略，元素可能可见或隐藏。
- **Visibility.visible**：该元素可能是可见的。


---
source: https://developer.apple.com/documentation/SwiftUI/Visibility/hidden
crawled: 2025-12-03T06:08:29Z
---

# Visibility.hidden

**Case**

The element may be hidden.

## Declaration

```swift
case hidden
```

## Discussion

Some APIs may use this value to represent a hint or preference, rather than a mandatory assertion. For example, setting confirmation dialog title visibility to `hidden` using the [confirmationDialog(_:isPresented:titleVisibility:actions:)](../View/confirmationDialog___isPresented_titleVisibility_actions.zh-Hans.md) modifier may not always hide the dialog title, which is required on some platforms.

## Getting visibility options

- **Visibility.automatic**: The element may be visible or hidden depending on the policies of the component accepting the visibility configuration.
- **Visibility.visible**: The element may be visible.

