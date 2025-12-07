--- 来源：https://developer.apple.com/documentation/SwiftUI/WindowPlacement/init(_:size3D:)

抓取时间：2025-12-01T10:21:16Z

---

# init(_:size3D:)

**Initializer**

创建一个新的窗口布局，可指定位置和 3D 尺寸。对于不支持深度的场景，深度将被忽略。

## 声明

```swift
init(_ position: WindowPlacement.Position? = nil, size3D: Size3D? = nil)
```

## 说明

任何未提供的值都将使用应用此布局的 `Scene` 的默认值。


---
source: https://developer.apple.com/documentation/SwiftUI/WindowPlacement/init(_:size3D:)
crawled: 2025-12-01T10:21:16Z
---

# init(_:size3D:)

**Initializer**

Creates a new window placement with an optional position and 3D size. Depth is ignored on scenes that don’t support it.

## Declaration

```swift
init(_ position: WindowPlacement.Position? = nil, size3D: Size3D? = nil)
```

## Discussion

Any values not provided will use use the default values for the `Scene` that this placement is being applied to.

