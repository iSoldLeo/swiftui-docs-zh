---
来源： https://developer.apple.com/documentation/SwiftUI/MenuOrder/automatic
抓取时间： 2025-12-03T06:23:55Z
---

# 自动

**类型属性**

系统为当前上下文选择的菜单排序。

## 声明

```swift
static let automatic: MenuOrder
```

## 讨论

在 iOS 上，对于在可滚动内容中显示的菜单，该顺序解析为 [fixed](fixed.zh-Hans.md)。使用[menu](../PickerStyle/menu.zh-Hans.md)样式的选取器也默认采用[fixed](fixed.zh-Hans.md)顺序。在所有其他情况下，菜单默认为[priority](priority.zh-Hans.md)顺序。

在 macOS、tvOS 和 watchOS 上，`automatic` 排序总是解析为[fixed](fixed.zh-Hans.md) 排序。

## 获取菜单订单

- **fixed**：从上到下订购项目。
- **priority**：保留最靠近用户交互点的第一个项目。


---
source: https://developer.apple.com/documentation/SwiftUI/MenuOrder/automatic
crawled: 2025-12-03T06:23:55Z
---

# automatic

**Type Property**

The ordering of the menu chosen by the system for the current context.

## Declaration

```swift
static let automatic: MenuOrder
```

## Discussion

On iOS, this order resolves to [fixed](fixed.zh-Hans.md) for menus presented within scrollable content. Pickers that use the [menu](../PickerStyle/menu.zh-Hans.md) style also default to [fixed](fixed.zh-Hans.md) order. In all other cases, menus default to [priority](priority.zh-Hans.md) order.

On macOS, tvOS and watchOS, the `automatic` order always resolves to [fixed](fixed.zh-Hans.md) order.

## Getting menu orders

- **fixed**: Order items from top to bottom.
- **priority**: Keep the first items closest to user’s interaction point.

