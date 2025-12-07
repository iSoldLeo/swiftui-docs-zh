--- 来源：https://developer.apple.com/documentation/swiftui/anytransition/slide

抓取时间：2025-12-04T13:17:03Z

---

# slide

**类型属性**

一种过渡效果，从前缘向内移动以插入，向后缘向外移动以移除。

## 声明

```swift
static var slide: AnyTransition { get }
```

## 讨论

## 获取内置过渡效果

- **identity**：一种过渡效果，将输入视图原封不动地作为输出视图返回。

- **move(edge:)**：一种过渡效果，将视图向指定的视图边缘移动。

- **offset(_:)**

- **offset(x:y:)**

- **opacity**：插入时从透明到不透明的过渡效果，移除时从不透明到透明的过渡效果。

- **push(from:)**：创建一个过渡效果，添加到视图后，视图插入时会从指定边缘向内移动并淡入，移除时会从另一边缘向外移动并淡出。

- **scale**：返回一个缩放视图的过渡效果。

- **scale(scale:anchor:)**：返回一个按指定比例缩放视图的过渡效果。


---
source: https://developer.apple.com/documentation/swiftui/anytransition/slide
crawled: 2025-12-04T13:17:03Z
---

# slide

**Type Property**

A transition that inserts by moving in from the leading edge, and removes by moving out towards the trailing edge.

## Declaration

```swift
static var slide: AnyTransition { get }
```

## Discussion



## Getting built-in transitions

- **identity**: A transition that returns the input view, unmodified, as the output view.
- **move(edge:)**: Returns a transition that moves the view away, towards the specified edge of the view.
- **offset(_:)**
- **offset(x:y:)**
- **opacity**: A transition from transparent to opaque on insertion, and from opaque to transparent on removal.
- **push(from:)**: Creates a transition that when added to a view will animate the view’s insertion by moving it in from the specified edge while fading it in, and animate its removal by moving it out towards the opposite edge and fading it out.
- **scale**: Returns a transition that scales the view.
- **scale(scale:anchor:)**: Returns a transition that scales the view by the specified amount.

