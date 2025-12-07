--- 来源：https://developer.apple.com/documentation/swiftui/anytransition/offset(x:y:)

抓取时间：2025-12-04T13:16:59Z

---

# offset(x:y:) | Apple 开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ AnyTransition ](/documentation/swiftui/anytransition)

- [ offset(x:y:) ](/documentation/swiftui/anytransition/offset(x:y:))

- [ AnyTransition ](/documentation/swiftui/anytransition)

- offset(x:y:) 

类型 方法# offset(x:y:)

iOS 13.0+、iPadOS 13.0+、Mac Catalyst 13.0+、macOS 10.15+、tvOS 13.0+、visionOS 1.0+、watchOS 6.0+

```
static func offset(
    x: CGFloat = 0,
    y: CGFloat = 0
) -> AnyTransition
```

## [另请参阅](/documentation/swiftui/anytransition/offset(x:y:)#see-also)

### [获取内置功能]过渡效果](/documentation/swiftui/anytransition/offset(x:y:)#获取内置过渡效果)

[`static var identity: AnyTransition`](/documentation/swiftui/anytransition/identity)返回输入视图（未修改）作为输出视图的过渡效果。[`static func move(edge: Edge) -> AnyTransition`](/documentation/swiftui/anytransition/move(edge:)返回一个将视图移向指定边缘的过渡效果。[`static func offset(CGSize) -> AnyTransition`](/documentation/swiftui/anytransition/offset(_:)[`static let opacity: AnyTransition`](/documentation/swiftui/anytransition/opacity)插入时从透明到不透明，移除时从不透明到透明的过渡效果。[`static func push(from: Edge) -> AnyTransition`](/documentation/swiftui/anytransition/push(from:)创建一个过渡效果，添加到视图后将为其添加动画效果。通过从指定边缘向内淡入插入视图，并通过向相反边缘向外淡出动画移除视图。[`static var scale: AnyTransition`](/documentation/swiftui/anytransition/scale)返回缩放视图的过渡效果。[`static func scale(scale: CGFloat, anchor: UnitPoint) -> AnyTransition`](/documentation/swiftui/anytransition/scale(scale:anchor:)返回按指定量缩放视图的过渡效果。[`static var slide: AnyTransition`](/documentation/swiftui/anytransition/slide)通过从前缘向内淡入插入，并通过向后缘向外淡出移除视图的过渡效果。

---
source: https://developer.apple.com/documentation/swiftui/anytransition/offset(x:y:)
crawled: 2025-12-04T13:16:59Z
---

# offset(x:y:) | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ AnyTransition ](/documentation/swiftui/anytransition)

- [ offset(x:y:) ](/documentation/swiftui/anytransition/offset(x:y:))

- [ AnyTransition ](/documentation/swiftui/anytransition)

-  offset(x:y:) 

Type Method# offset(x:y:)

iOS 13.0+iPadOS 13.0+Mac Catalyst 13.0+macOS 10.15+tvOS 13.0+visionOS 1.0+watchOS 6.0+

```
static func offset(
    x: CGFloat = 0,
    y: CGFloat = 0
) -> AnyTransition
```

## [See Also](/documentation/swiftui/anytransition/offset(x:y:)#see-also)

### [Getting built-in transitions](/documentation/swiftui/anytransition/offset(x:y:)#Getting-built-in-transitions)

[`static var identity: AnyTransition`](/documentation/swiftui/anytransition/identity)A transition that returns the input view, unmodified, as the output view.[`static func move(edge: Edge) -> AnyTransition`](/documentation/swiftui/anytransition/move(edge:))Returns a transition that moves the view away, towards the specified edge of the view.[`static func offset(CGSize) -> AnyTransition`](/documentation/swiftui/anytransition/offset(_:))[`static let opacity: AnyTransition`](/documentation/swiftui/anytransition/opacity)A transition from transparent to opaque on insertion, and from opaque to transparent on removal.[`static func push(from: Edge) -> AnyTransition`](/documentation/swiftui/anytransition/push(from:))Creates a transition that when added to a view will animate the view’s insertion by moving it in from the specified edge while fading it in, and animate its removal by moving it out towards the opposite edge and fading it out.[`static var scale: AnyTransition`](/documentation/swiftui/anytransition/scale)Returns a transition that scales the view.[`static func scale(scale: CGFloat, anchor: UnitPoint) -> AnyTransition`](/documentation/swiftui/anytransition/scale(scale:anchor:))Returns a transition that scales the view by the specified amount.[`static var slide: AnyTransition`](/documentation/swiftui/anytransition/slide)A transition that inserts by moving in from the leading edge, and removes by moving out towards the trailing edge.