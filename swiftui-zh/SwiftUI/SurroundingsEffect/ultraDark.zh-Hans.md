---
来源： https://developer.apple.com/documentation/SwiftUI/SurroundingsEffect/ultraDark
抓取时间： 2025-12-03T06:08:36Z
---

# 超暗

**类型属性**

使直通视频的暗度超过 [dark](dark.zh-Hans.md) 的效果

## 声明

```swift
static var ultraDark: SurroundingsEffect { get }
```

## 讨论

当您想在显示特定视图时调暗直通视频时，请将[preferredSurroundingsEffect(_:)](../View/preferredsurroundingseffect.zh-Hans.md) 视图修饰符与此值一起使用。这样做有助于吸引人们对应用程序内容的注意力，同时还能让人们保持对周围环境的关注。只有在打开沉浸式空间时才会应用此效果。


---
source: https://developer.apple.com/documentation/SwiftUI/SurroundingsEffect/ultraDark
crawled: 2025-12-03T06:08:36Z
---

# ultraDark

**Type Property**

An effect that dims passthrough video more than [dark](dark.zh-Hans.md)

## Declaration

```swift
static var ultraDark: SurroundingsEffect { get }
```

## Discussion

Use this value with the [preferredSurroundingsEffect(_:)](../View/preferredsurroundingseffect.zh-Hans.md) view modifier when you want to dim passthrough video while displaying a particular view. Doing so helps to draw attention to your app’s content while still enabling people to remain aware of their surroundings. This effect will only be applied while an immersive space is opened.

