---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/presentationMode
抓取时间： 2025-12-03T06:07:35Z
---

# 演示模式

**实例属性**

与此环境关联的视图的当前呈现模式的绑定。

## 声明

```swift
var presentationMode: Binding<PresentationMode> { get }
```

## 过时的环境值

- **disableAutocorrection**：布尔值，用于确定视图层次结构是否启用了自动更正功能。
- **sizeCategory**：内容的大小。
- **PresentationMode**：内容大小：显示一个视图当前是否由另一个视图显示。
- **complicationRenderingMode**：当前环境的复杂度渲染模式。
- **controlActiveState**：窗口中控件的预期活动外观。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/presentationMode
crawled: 2025-12-03T06:07:35Z
---

# presentationMode

**Instance Property**

A binding to the current presentation mode of the view associated with this environment.

## Declaration

```swift
var presentationMode: Binding<PresentationMode> { get }
```

## Deprecated environment values

- **disableAutocorrection**: A Boolean value that determines whether the view hierarchy has auto-correction enabled.
- **sizeCategory**: The size of content.
- **PresentationMode**: An indication whether a view is currently presented by another view.
- **complicationRenderingMode**: The complication rendering mode for the current environment.
- **controlActiveState**: The active appearance expected of controls in a window.

