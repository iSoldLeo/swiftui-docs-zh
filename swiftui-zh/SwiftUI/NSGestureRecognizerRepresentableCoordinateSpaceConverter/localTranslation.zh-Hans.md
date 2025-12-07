---
来源： https://developer.apple.com/documentation/SwiftUI/NSGestureRecognizerRepresentableCoordinateSpaceConverter/localTranslation
抓取时间： 2025-12-03T06:58:09Z
---

# 本地翻译

**实例属性**

所代表的手势识别器在其所连接的 SwiftUI 视图坐标空间中的当前平移值，如果所代表的手势识别器不响应`-translationInView:` 选择器，则为`nil`。

### 声明

```swift
var localTranslation: CGPoint? { get }
```


---
source: https://developer.apple.com/documentation/SwiftUI/NSGestureRecognizerRepresentableCoordinateSpaceConverter/localTranslation
crawled: 2025-12-03T06:58:09Z
---

# localTranslation

**Instance Property**

The represented gesture recognizer’s current translation in the coordinate space of the SwiftUI view it’s attached to, or `nil` if the represented gesture recognizer doesn’t respond to `-translationInView:` selector.

## Declaration

```swift
var localTranslation: CGPoint? { get }
```

