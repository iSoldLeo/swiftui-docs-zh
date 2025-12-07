--- 来源：https://developer.apple.com/documentation/SwiftUI/View/tabletopGame(_:parent:automaticUpdate:interaction:)

抓取时间：2025-12-02T17:26:03Z

---

# tabletopGame(_:parent:automaticUpdate:interaction:)

**实例方法**

提供一个闭包，该闭包会在需要时返回一个新的交互。

## 声明

```swift
@MainActor @preconcurrency func tabletopGame(_ game: TabletopGame, parent: Entity, automaticUpdate: Bool = true, interaction make: @escaping (TabletopInteraction.Value) -> any TabletopInteraction.Delegate) -> some View

```

## 创建桌面游戏

- **tabletopGame(_:parent:automaticUpdate:)**：向视图添加桌面游戏。


---
source: https://developer.apple.com/documentation/SwiftUI/View/tabletopGame(_:parent:automaticUpdate:interaction:)
crawled: 2025-12-02T17:26:03Z
---

# tabletopGame(_:parent:automaticUpdate:interaction:)

**Instance Method**

Supplies a closure which returns a new interaction whenever needed.

## Declaration

```swift
@MainActor @preconcurrency func tabletopGame(_ game: TabletopGame, parent: Entity, automaticUpdate: Bool = true, interaction make: @escaping (TabletopInteraction.Value) -> any TabletopInteraction.Delegate) -> some View

```

## Creating a tabletop game

- **tabletopGame(_:parent:automaticUpdate:)**: Adds a tabletop game to a view.

