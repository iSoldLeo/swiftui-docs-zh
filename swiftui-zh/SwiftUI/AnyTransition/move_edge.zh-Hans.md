--- 来源：https://developer.apple.com/documentation/swiftui/anytransition/move(edge:)

抓取时间：2025-12-04T13:16:52Z

---

# move(edge:)

**类型方法**

返回一个过渡效果，该效果使视图向指定的视图边缘移动。

## 声明

```swift
static func move(edge: Edge) -> AnyTransition
```

## 获取内置过渡效果

- **identity**：一个过渡效果，它将输入视图原封不动地作为输出视图返回。

- **offset(_:)**

- **offset(x:y:)**

- **opacity**：一个过渡效果，插入时从透明变为不透明，移除时从不透明变为透明。

- **push(from:)**：创建一个过渡效果，添加到视图后，视图插入时会从指定边缘向内移动并淡入，移除时会从另一边缘向外移动并淡出。

- **scale**：返回一个缩放视图的过渡效果。

- **scale(scale:anchor:)**：返回一个按指定比例缩放视图的过渡效果。

- **slide**：一个从前缘向内移动插入视图，向后缘向外移动移除视图的过渡效果。


---
source: https://developer.apple.com/documentation/swiftui/anytransition/move(edge:)
crawled: 2025-12-04T13:16:52Z
---

# move(edge:)

**Type Method**

Returns a transition that moves the view away, towards the specified edge of the view.

## Declaration

```swift
static func move(edge: Edge) -> AnyTransition
```

## Getting built-in transitions

- **identity**: A transition that returns the input view, unmodified, as the output view.
- **offset(_:)**
- **offset(x:y:)**
- **opacity**: A transition from transparent to opaque on insertion, and from opaque to transparent on removal.
- **push(from:)**: Creates a transition that when added to a view will animate the view’s insertion by moving it in from the specified edge while fading it in, and animate its removal by moving it out towards the opposite edge and fading it out.
- **scale**: Returns a transition that scales the view.
- **scale(scale:anchor:)**: Returns a transition that scales the view by the specified amount.
- **slide**: A transition that inserts by moving in from the leading edge, and removes by moving out towards the trailing edge.

