--- 来源：https://developer.apple.com/documentation/SwiftUI/WindowPlacement/init(_:width:height:)

抓取时间：2025-12-01T10:21:17Z

---

# init(_:width:height:)

**Initializer**

创建一个新的窗口布局，其位置与显示位置相关，宽度和高度可选。

## 声明

```swift
init(_ position: UnitPoint, width: CGFloat? = nil, height: CGFloat? = nil)
```

## 说明

任何未提供的值都将使用应用此布局的 `Scene` 的默认值。


---
source: https://developer.apple.com/documentation/SwiftUI/WindowPlacement/init(_:width:height:)
crawled: 2025-12-01T10:21:17Z
---

# init(_:width:height:)

**Initializer**

Creates a new window placement with a display-relative position, with an optional width and height.

## Declaration

```swift
init(_ position: UnitPoint, width: CGFloat? = nil, height: CGFloat? = nil)
```

## Discussion

Any values not provided will use use the default values for the `Scene` that this placement is being applied to.

