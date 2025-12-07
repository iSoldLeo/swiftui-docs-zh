---
来源： https://developer.apple.com/documentation/SwiftUI/ScrollBounceBehavior/basedOnSize
抓取时间： 2025-12-03T06:43:06Z
---

# basedOnSize

**类型属性**

当滚动视图的内容大到需要滚动时，该视图会弹起。

## 声明

```swift
static var basedOnSize: ScrollBounceBehavior { get }
```

## 讨论

如果内容的大小超出了滚动视图在指定轴上的大小，滚动视图会沿指定轴反弹。

## 反弹行为

- **automatic**：自动行为。
- **always**：自动行为：滚动视图始终跳动。


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollBounceBehavior/basedOnSize
crawled: 2025-12-03T06:43:06Z
---

# basedOnSize

**Type Property**

The scrollable view bounces when its content is large enough to require scrolling.

## Declaration

```swift
static var basedOnSize: ScrollBounceBehavior { get }
```

## Discussion

The scrollable view bounces along the specified axis if the size of the content exceeeds the size of the scrollable view in that axis.

## Bounce behaviors

- **automatic**: The automatic behavior.
- **always**: The scrollable view always bounces.

