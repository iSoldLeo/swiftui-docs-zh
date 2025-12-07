--- 来源：https://developer.apple.com/documentation/SwiftUI/MenuActionDismissBehavior/automatic

抓取时间：2025-12-03T06:23:53Z

---

# automatic

**Type 属性**

使用适合当前上下文的菜单关闭行为。

## 声明

```swift
static let automatic: MenuActionDismissBehavior
```

## 讨论

大多数情况下，默认行为是 [enabled](enabled.zh-Hans.md)。某些情况下，例如 [Stepper](../Stepper.zh-Hans.md)，默认使用 [disabled](disabled.zh-Hans.md)。

## 获取菜单关闭行为

- **disabled**：执行操作后，从不关闭当前菜单。

- **enabled**：执行操作后，始终关闭当前菜单。


---
source: https://developer.apple.com/documentation/SwiftUI/MenuActionDismissBehavior/automatic
crawled: 2025-12-03T06:23:53Z
---

# automatic

**Type Property**

Use the a dismissal behavior that’s appropriate for the given context.

## Declaration

```swift
static let automatic: MenuActionDismissBehavior
```

## Discussion

In most cases, the default behavior is [enabled](enabled.zh-Hans.md). There are some cases, like [Stepper](../Stepper.zh-Hans.md), that use [disabled](disabled.zh-Hans.md) by default.

## Getting dismiss behaviors

- **disabled**: Never dismiss the presented menu after performing an action.
- **enabled**: Always dismiss the presented menu after performing an action.

