---
来源： https://developer.apple.com/documentation/SwiftUI/WindowManagerRole/automatic
抓取时间： 2025-12-03T05:32:32Z
---

# 自动

**类型属性**

自动角色。场景的类型和配置将用于确定其窗口在全屏和舞台管理器中的行为方式。

## 声明

```swift
static let automatic: WindowManagerRole
```

## 讨论

在 macOS 上，[WindowGroup](../WindowGroup.zh-Hans.md) 和 [DocumentGroup](../DocumentGroup.zh-Hans.md) 场景将使用`principal` 角色。[Window](../Window.zh-Hans.md)场景在应用程序定义中被指定为第一个场景时将使用`principal`角色，否则将使用`associated`角色。[Settings](../Settings.zh-Hans.md)将使用`associated`角色。


---
source: https://developer.apple.com/documentation/SwiftUI/WindowManagerRole/automatic
crawled: 2025-12-03T05:32:32Z
---

# automatic

**Type Property**

The automatic role. The type and configuration of the scene will be used to determine how its windows behave in full screen and Stage Manager.

## Declaration

```swift
static let automatic: WindowManagerRole
```

## Discussion

On macOS, [WindowGroup](../WindowGroup.zh-Hans.md) and [DocumentGroup](../DocumentGroup.zh-Hans.md) scenes will use the `principal` role. [Window](../Window.zh-Hans.md) scenes will use the `principal` role when they are specified as the first scene in the app’s definition, and use the `associated` role otherwise. [Settings](../Settings.zh-Hans.md) will use the `associated` role.

