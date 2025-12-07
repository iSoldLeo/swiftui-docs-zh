--- 来源：https://developer.apple.com/documentation/SwiftUI/WindowPlacement/init(_:width:height:depth:)

抓取时间：2025-12-01T10:21:19Z

---

# init(_:width:height:depth:)

**Initializer**

创建一个新的窗口布局，可以指定位置和 3D 尺寸（可选）。在不支持深度的场景或平台上，深度值将被忽略。

## 声明

```swift
init(_ position: WindowPlacement.Position? = nil, width: CGFloat? = nil, height: CGFloat? = nil, depth: CGFloat? = nil)
```

## 说明

任何未提供的值都将使用应用此布局的 `Scene` 的默认值。


---
source: https://developer.apple.com/documentation/SwiftUI/WindowPlacement/init(_:width:height:depth:)
crawled: 2025-12-01T10:21:19Z
---

# init(_:width:height:depth:)

**Initializer**

Creates a new window placement with an optional position and 3D size. Depth is ignored on scenes or platforms that don’t support it.

## Declaration

```swift
init(_ position: WindowPlacement.Position? = nil, width: CGFloat? = nil, height: CGFloat? = nil, depth: CGFloat? = nil)
```

## Discussion

Any values not provided will use use the default values for the `Scene` that this placement is being applied to.

