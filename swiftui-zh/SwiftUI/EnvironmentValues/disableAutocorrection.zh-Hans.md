---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/disableAutocorrection
抓取时间： 2025-12-03T06:07:33Z
---

# disableAutocorrection

**实例属性**

布尔值，用于确定视图层次结构是否启用了自动更正功能。

## 声明

```swift
var disableAutocorrection: Bool? { get set }
```

## 讨论

当值为`nil` 时，SwiftUI 使用系统默认值。默认值为 `nil`。

## 过时的环境值

- **sizeCategory**：内容的大小。
- **presentationMode**：与此环境关联的视图的当前显示模式的绑定。
- **PresentationMode**：指示一个视图当前是否由另一个视图呈现。
- **complicationRenderingMode**：当前环境的复杂度渲染模式。
- **controlActiveState**：窗口中控件的预期活动外观。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/disableAutocorrection
crawled: 2025-12-03T06:07:33Z
---

# disableAutocorrection

**Instance Property**

A Boolean value that determines whether the view hierarchy has auto-correction enabled.

## Declaration

```swift
var disableAutocorrection: Bool? { get set }
```

## Discussion

When the value is `nil`, SwiftUI uses the system default. The default value is `nil`.

## Deprecated environment values

- **sizeCategory**: The size of content.
- **presentationMode**: A binding to the current presentation mode of the view associated with this environment.
- **PresentationMode**: An indication whether a view is currently presented by another view.
- **complicationRenderingMode**: The complication rendering mode for the current environment.
- **controlActiveState**: The active appearance expected of controls in a window.

