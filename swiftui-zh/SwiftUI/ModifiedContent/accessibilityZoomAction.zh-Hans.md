---
来源： https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityZoomAction(_:)
抓取时间： 2025-11-30T21:32:05Z
---

# accessibilityZoomAction(_:)

**实例方法**

为视图添加无障碍缩放操作。该操作允许 VoiceOver 等辅助技术通过调用该操作与视图进行交互。

### 声明

```swift
nonisolated func accessibilityZoomAction(_ handler: @escaping (AccessibilityZoomGestureAction) -> Void) -> ModifiedContent<Content, Modifier>
```

## 讨论

例如，缩放操作就是这样用来转换具有`MagnificationGesture`的形状的比例的。

```swift
var body: some View {
    Circle()
        .scaleEffect(magnifyBy)
        .gesture(magnification)
        .accessibilityLabel("Circle Magnifier")
        .accessibilityZoomAction { action in
            switch action.direction {
            case .zoomIn:
                magnifyBy += 0.5
            case .zoomOut:
                 magnifyBy -= 0.5
            }
        }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityZoomAction(_:)
crawled: 2025-11-30T21:32:05Z
---

# accessibilityZoomAction(_:)

**Instance Method**

Adds an accessibility zoom action to the view. Actions allow assistive technologies, such as VoiceOver, to interact with the view by invoking the action.

## Declaration

```swift
nonisolated func accessibilityZoomAction(_ handler: @escaping (AccessibilityZoomGestureAction) -> Void) -> ModifiedContent<Content, Modifier>
```

## Discussion

For example, this is how a zoom action is used to transform the scale of a shape which has a `MagnificationGesture`.

```swift
var body: some View {
    Circle()
        .scaleEffect(magnifyBy)
        .gesture(magnification)
        .accessibilityLabel("Circle Magnifier")
        .accessibilityZoomAction { action in
            switch action.direction {
            case .zoomIn:
                magnifyBy += 0.5
            case .zoomOut:
                 magnifyBy -= 0.5
            }
        }
}
```

