---
来源： https://developer.apple.com/documentation/SwiftUI/ToolbarDefaultItemKind/search
抓取时间： 2025-12-03T06:05:01Z
---

# 搜索

**类型属性**

由`View/searchable(text:isPresented:placement:prompt)`修饰符添加的搜索项。

## 声明

```swift
static let search: ToolbarDefaultItemKind
```

## 讨论

使用`.search`默认项目种类和`DefaultToolbarItem/init(kind:placment:)`自定义默认项目种类的[ToolbarItemPlacement](../ToolbarItemPlacement.zh-Hans.md)。搜索默认项目种类只能放在 iPhone 的`.bottomBar` 中。所有可用平台都支持 `.topBarTrailing` 和 `.automatic`。


---
source: https://developer.apple.com/documentation/SwiftUI/ToolbarDefaultItemKind/search
crawled: 2025-12-03T06:05:01Z
---

# search

**Type Property**

The search item added by a `View/searchable(text:isPresented:placement:prompt)` modifier.

## Declaration

```swift
static let search: ToolbarDefaultItemKind
```

## Discussion

Use a `.search` default item kind with `DefaultToolbarItem/init(kind:placment:)` to customize the [ToolbarItemPlacement](../ToolbarItemPlacement.zh-Hans.md) of a default item kind. The search default item kind can be placed in the `.bottomBar` on iPhone only. All available platforms support `.topBarTrailing` and `.automatic`.

