--- 来源：https://developer.apple.com/documentation/SwiftUI/AnyTransition/push(from:)

抓取时间：2025-12-03T06:16:59Z

---

# push(from:)

**类型方法**

创建一个过渡效果，添加到视图后，视图插入时会从指定边缘淡入，移除时会淡出。

## 声明

```swift
static func push(from edge: Edge) -> AnyTransition
```

## 参数

- **edge**：视图动画进入的边缘。

## 返回值

一个通过移动和淡入淡出来为视图添加动画效果的过渡效果。

## 获取内置过渡效果

- **identity**：返回输入视图（未修改）作为输出视图的过渡效果。

- **move(edge:)**：返回将视图向指定边缘移动的过渡效果。

- **offset(_:)**

- **offset(x:y:)**

- **opacity**：插入时从透明变为不透明，移除时从不透明变为透明的过渡效果。

- **scale**：返回缩放视图的过渡效果。

- **scale(scale:anchor:)**：返回按指定比例缩放视图的过渡效果。

- **slide**：从前缘向内插入，向后缘向外移除的过渡效果。


---
source: https://developer.apple.com/documentation/SwiftUI/AnyTransition/push(from:)
crawled: 2025-12-03T06:16:59Z
---

# push(from:)

**Type Method**

Creates a transition that when added to a view will animate the view’s insertion by moving it in from the specified edge while fading it in, and animate its removal by moving it out towards the opposite edge and fading it out.

## Declaration

```swift
static func push(from edge: Edge) -> AnyTransition
```

## Parameters

- **edge**: The edge from which the view will be animated in.

## Return Value

A transition that animates a view by moving and fading it.

## Getting built-in transitions

- **identity**: A transition that returns the input view, unmodified, as the output view.
- **move(edge:)**: Returns a transition that moves the view away, towards the specified edge of the view.
- **offset(_:)**
- **offset(x:y:)**
- **opacity**: A transition from transparent to opaque on insertion, and from opaque to transparent on removal.
- **scale**: Returns a transition that scales the view.
- **scale(scale:anchor:)**: Returns a transition that scales the view by the specified amount.
- **slide**: A transition that inserts by moving in from the leading edge, and removes by moving out towards the trailing edge.

