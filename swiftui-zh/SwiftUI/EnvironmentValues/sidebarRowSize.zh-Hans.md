---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/sidebarRowSize
抓取时间： 2025-12-02T17:29:38Z
---

# 侧边栏行列大小

**实例属性**

侧边栏行的当前大小。

## 声明

```swift
var sidebarRowSize: SidebarRowSize { get set }
```

## 讨论

在 macOS 上，反映系统设置的外观设置中 "侧边栏图标大小 "的值。

这可用于更新侧边栏中显示的内容，以适应该尺寸。此外，它还可以被覆盖，以强制侧边栏使用特定大小，而不受用户偏好的影响。

在其他平台上，该值始终为 `.medium`，设置不同的值不会有任何影响。

SwiftUI 视图（如 `Label` 视图）会自动适应侧边栏的行大小。

## 配置侧边栏

- **SidebarRowSize**：侧边栏行的标准尺寸。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/sidebarRowSize
crawled: 2025-12-02T17:29:38Z
---

# sidebarRowSize

**Instance Property**

The current size of sidebar rows.

## Declaration

```swift
var sidebarRowSize: SidebarRowSize { get set }
```

## Discussion

On macOS, reflects the value of the “Sidebar icon size” in System Settings’ Appearance settings.

This can be used to update the content shown in the sidebar in response to this size. And it can be overridden to force a sidebar to a particularly size, regardless of the user preference.

On other platforms, the value is always `.medium` and setting a different value has no effect.

SwiftUI views like `Label` automatically adapt to the sidebar row size.

## Configuring the sidebar

- **SidebarRowSize**: The standard sizes of sidebar rows.

