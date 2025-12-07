---
来源： https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityDirectTouch(_:options:)
抓取时间：2025-11-30T21:31:46Z
---

# accessibilityDirectTouch(_:options:)

**实例方法**

明确设置此辅助功能元素是否为直接触摸区域。直接触摸区域将触摸事件传递给应用程序，而不是通过 VoiceOver 等辅助技术来处理。修改器接受一个可选的 `AccessibilityDirectTouchOptions`选项设置，以自定义直接触摸区域的功能。

### 声明

```swift
nonisolated func accessibilityDirectTouch(_ isDirectTouchArea: Bool = true, options: AccessibilityDirectTouchOptions = []) -> ModifiedContent<Content, Modifier>
```

## 讨论

例如，直接触摸区域可以让 VoiceOver 用户与由`rotationEffect` 控制的`RotationGesture` 视图进行交互。直接触摸区域要求用户在使用直接触摸区域之前先激活该区域。

```swift
var body: some View {
    Rectangle()
        .frame(width: 200, height: 200, alignment: .center)
        .rotationEffect(angle)
        .gesture(rotation)
        .accessibilityDirectTouch(options: .requiresActivation)
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityDirectTouch(_:options:)
crawled: 2025-11-30T21:31:46Z
---

# accessibilityDirectTouch(_:options:)

**Instance Method**

Explicitly set whether this accessibility element is a direct touch area. Direct touch areas passthrough touch events to the app rather than being handled through an assistive technology, such as VoiceOver. The modifier accepts an optional `AccessibilityDirectTouchOptions` option set to customize the functionality of the direct touch area.

## Declaration

```swift
nonisolated func accessibilityDirectTouch(_ isDirectTouchArea: Bool = true, options: AccessibilityDirectTouchOptions = []) -> ModifiedContent<Content, Modifier>
```

## Discussion

For example, this is how a direct touch area would allow a VoiceOver user to interact with a view with a `rotationEffect` controlled by a `RotationGesture`. The direct touch area would require a user to activate the area before using the direct touch area.

```swift
var body: some View {
    Rectangle()
        .frame(width: 200, height: 200, alignment: .center)
        .rotationEffect(angle)
        .gesture(rotation)
        .accessibilityDirectTouch(options: .requiresActivation)
}
```

