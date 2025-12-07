---
来源： https://developer.apple.com/documentation/SwiftUI/UIGestureRecognizerRepresentableCoordinateSpaceConverter/localTranslation
抓取时间： 2025-12-03T07:00:57Z
---

# 本地翻译

**实例属性**

所代表的手势识别器在其所连接的 SwiftUI 视图坐标空间中的当前平移。

## 声明

```swift
var localTranslation: CGPoint? { get }
```

## 讨论

如果手势识别器没有实现`translationInView:`方法，则返回 nil。


---
source: https://developer.apple.com/documentation/SwiftUI/UIGestureRecognizerRepresentableCoordinateSpaceConverter/localTranslation
crawled: 2025-12-03T07:00:57Z
---

# localTranslation

**Instance Property**

The represented gesture recognizer’s current translation in the coordinate space of the SwiftUI view it’s attached to.

## Declaration

```swift
var localTranslation: CGPoint? { get }
```

## Discussion

If the gesture recognizer does not implement a `translationInView:` method, returns nil.

