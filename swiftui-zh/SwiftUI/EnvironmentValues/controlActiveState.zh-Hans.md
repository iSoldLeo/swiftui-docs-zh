---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/controlActiveState
抓取时间： 2025-12-03T06:07:37Z
---

# 控制活动状态

**实例属性**

窗口中控件的预期活动外观。

## 声明

```swift
var controlActiveState: ControlActiveState { get set }
```

## 讨论

`ControlActiveState` 和 `EnvironmentValues.controlActiveState` 已被弃用，请使用 `EnvironmentValues.appearsActive` 代替。

从 macOS 15.0 开始，该环境属性值与`EnvironmentValues.appearsActive` 之间的严格映射关系如下：

- `appearsActive == true`, `controlActiveState` 返回 `.key`
- `appearsActive == false`, `controlActiveState` 返回 `.inactive`
- `controlActiveState` 设置为 `.key` 或 `.active` 时，`appearsActive` 将设置为 `true`。
- `controlActiveState` 设置为 `.inactive`，`appearsActive` 将设置为 `false`。

## 过时的环境值

- **disableAutocorrection**：布尔值，用于确定视图层次结构是否启用了自动更正功能。
- **sizeCategory**：内容的大小。
- **presentationMode**：内容的大小：与该环境关联的视图的当前显示模式的绑定。
- **PresentationMode**：指示一个视图当前是否由另一个视图呈现。
- **complicationRenderingMode**：当前环境的复杂度渲染模式。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/controlActiveState
crawled: 2025-12-03T06:07:37Z
---

# controlActiveState

**Instance Property**

The active appearance expected of controls in a window.

## Declaration

```swift
var controlActiveState: ControlActiveState { get set }
```

## Discussion

`ControlActiveState` and `EnvironmentValues.controlActiveState` are deprecated, use `EnvironmentValues.appearsActive` instead.

Starting with macOS 15.0, the value of this environment property is strictly mapped to and from `EnvironmentValues.appearsActive` as follows:

- `appearsActive == true`, `controlActiveState` returns `.key`
- `appearsActive == false`, `controlActiveState` returns `.inactive`
- `controlActiveState` is set to `.key` or `.active`, `appearsActive` will be set to `true`.
- `controlActiveState` is set to `.inactive`, `appearsActive` will be set to `false`.

## Deprecated environment values

- **disableAutocorrection**: A Boolean value that determines whether the view hierarchy has auto-correction enabled.
- **sizeCategory**: The size of content.
- **presentationMode**: A binding to the current presentation mode of the view associated with this environment.
- **PresentationMode**: An indication whether a view is currently presented by another view.
- **complicationRenderingMode**: The complication rendering mode for the current environment.

