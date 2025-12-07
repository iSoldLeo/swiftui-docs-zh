--- 来源：https://developer.apple.com/documentation/SwiftUI/PresentationMode

抓取时间：2025-12-03T06:07:36Z

---

# PresentationMode

**Structure**

指示当前视图是否由另一个视图呈现。

## 声明

```swift
struct PresentationMode
```

## 检查呈现状态

- **isPresented**：指示当前视图是否正在呈现。

## 关闭呈现状态

- **dismiss()**：如果当前视图正在呈现，则将其关闭。

## 已弃用的环境变量值

- **disableAutocorrection**：一个布尔值，用于确定视图层次结构是否启用了自动纠错。

- **sizeCategory**：内容大小。

- **presentationMode**：与此环境关联的视图的当前呈现模式绑定。

- **complicationRenderingMode**：当前环境的复杂渲染模式。

- **controlActiveState**：窗口中控件的预期活动外观。


---
source: https://developer.apple.com/documentation/SwiftUI/PresentationMode
crawled: 2025-12-03T06:07:36Z
---

# PresentationMode

**Structure**

An indication whether a view is currently presented by another view.

## Declaration

```swift
struct PresentationMode
```

## Checking presentation

- **isPresented**: Indicates whether a view is currently presented.

## Dismissing presentation

- **dismiss()**: Dismisses the view if it is currently presented.

## Deprecated environment values

- **disableAutocorrection**: A Boolean value that determines whether the view hierarchy has auto-correction enabled.
- **sizeCategory**: The size of content.
- **presentationMode**: A binding to the current presentation mode of the view associated with this environment.
- **complicationRenderingMode**: The complication rendering mode for the current environment.
- **controlActiveState**: The active appearance expected of controls in a window.

