--- 来源：https://developer.apple.com/documentation/swiftui/anytransition/scale(scale:anchor:)

抓取时间：2025-12-04T13:17:02Z

---

# scale(scale:anchor:)

**类型方法**

返回一个将视图按指定比例缩放的过渡效果。

## 声明

```swift
static func scale(scale: CGFloat, anchor: UnitPoint = .center) -> AnyTransition
```

## 获取内置过渡效果

- **identity**：返回一个将输入视图原样返回为输出视图的过渡效果。

- **move(edge:)**：返回一个将视图移向指定边缘的过渡效果。

- **offset(_:)**

- **offset(x:y:)**

- **opacity**：插入时从透明到不透明的过渡效果，移除时从不透明到透明的过渡效果。

- **push(from:)**：创建一个过渡效果，添加到视图后，视图插入时会从指定边缘向内移动并淡入，移除时会从另一边缘向外移动并淡出。

- **scale**：返回一个缩放视图的过渡效果。

- **slide**：插入时从前缘向内移动，移除时向后缘向外移动。


---
source: https://developer.apple.com/documentation/swiftui/anytransition/scale(scale:anchor:)
crawled: 2025-12-04T13:17:02Z
---

# scale(scale:anchor:)

**Type Method**

Returns a transition that scales the view by the specified amount.

## Declaration

```swift
static func scale(scale: CGFloat, anchor: UnitPoint = .center) -> AnyTransition
```

## Getting built-in transitions

- **identity**: A transition that returns the input view, unmodified, as the output view.
- **move(edge:)**: Returns a transition that moves the view away, towards the specified edge of the view.
- **offset(_:)**
- **offset(x:y:)**
- **opacity**: A transition from transparent to opaque on insertion, and from opaque to transparent on removal.
- **push(from:)**: Creates a transition that when added to a view will animate the view’s insertion by moving it in from the specified edge while fading it in, and animate its removal by moving it out towards the opposite edge and fading it out.
- **scale**: Returns a transition that scales the view.
- **slide**: A transition that inserts by moving in from the leading edge, and removes by moving out towards the trailing edge.

