---
来源： https://developer.apple.com/documentation/SwiftUI/MenuActionDismissBehavior
抓取时间： 2025-12-02T17:36:31Z
---

# MenuActionDismissBehavior

**Structure**

菜单取消行为选项集。

## 声明

```swift
struct MenuActionDismissBehavior
```

## 概览

使用 [menuActionDismissBehavior(_:)](View/menuActionDismissBehavior.zh-Hans.md) 视图修改器为视图层次结构配置菜单取消行为。

## 获取取消行为

- **automatic**：使用适合给定上下文的解雇行为。
- **disabled**：在执行操作后永远不要取消显示的菜单。
- **enabled**：执行操作后始终退出显示的菜单。

## 配置菜单退出

- **menuActionDismissBehavior(_:)**：告诉菜单是否在执行操作后解散。

## 符合

- 等价


---
source: https://developer.apple.com/documentation/SwiftUI/MenuActionDismissBehavior
crawled: 2025-12-02T17:36:31Z
---

# MenuActionDismissBehavior

**Structure**

The set of menu dismissal behavior options.

## Declaration

```swift
struct MenuActionDismissBehavior
```

## Overview

Configure the menu dismissal behavior for a view hierarchy using the [menuActionDismissBehavior(_:)](View/menuActionDismissBehavior.zh-Hans.md) view modifier.

## Getting dismiss behaviors

- **automatic**: Use the a dismissal behavior that’s appropriate for the given context.
- **disabled**: Never dismiss the presented menu after performing an action.
- **enabled**: Always dismiss the presented menu after performing an action.

## Configuring menu dismissal

- **menuActionDismissBehavior(_:)**: Tells a menu whether to dismiss after performing an action.

## Conforms To

- Equatable

