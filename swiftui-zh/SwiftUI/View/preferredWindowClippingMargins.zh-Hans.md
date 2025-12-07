--- 来源：https://developer.apple.com/documentation/SwiftUI/View/preferredWindowClippingMargins(_:_:)

抓取时间：2025-11-30T19:49:48Z

---

# preferredWindowClippingMargins(_:_:)

**实例方法**

请求在窗口边界之外绘制内容时添加额外的边距。

## 声明

```swift
@MainActor @preconcurrency func preferredWindowClippingMargins(_ edges: Edge3D.Set = .all, _ length: CGFloat?) -> some View

```

## 参数

- **edges**：需要添加边距的边缘。

- **length**：每个指定边缘请求的边距大小。

## 说明

此修饰符仅对窗口样式为 `.volumetric` 的窗口生效。

窗口的边界取决于其内容，可通过拖动角点来调整大小。默认情况下，系统会裁剪超出窗口边界的内容。此修改器请求额外的空间用于在窗口边界之外绘制内容。您可以使用此空间渲染额外的视觉效果，以增强应用程序的视觉冲击力。此内容不接收事件，并且可能随时被系统裁剪。

此修改器提供的额外边距并非绝对保证，系统可能会更新或减少这些边距。每次系统更新当前边距时，都会更新环境中的 `windowClippingMargins` 值。

如果多个视图请求边距，则场景的首选边距将是每个视图的首选边距的最大值。例如，如果一个视图需要 `400` 的前边距，而另一个视图需要 `400` 的后边距，则场景将同时请求 `400` 的前边距和后边距。如果一个视图请求前导边距为`200`，而另一个视图请求前导边距为`300`，则场景将请求`300`。


---
source: https://developer.apple.com/documentation/SwiftUI/View/preferredWindowClippingMargins(_:_:)
crawled: 2025-11-30T19:49:48Z
---

# preferredWindowClippingMargins(_:_:)

**Instance Method**

Requests additional margins for drawing beyond the bounds of the window.

## Declaration

```swift
@MainActor @preconcurrency func preferredWindowClippingMargins(_ edges: Edge3D.Set = .all, _ length: CGFloat?) -> some View

```

## Parameters

- **edges**: The edges that should receive margins.
- **length**: The amount of margin requested on each specified edge.

## Discussion

This modifier will only have an effect on windows with a `.volumetric` window style.

A window’s bounds are based on its content, and resizable by dragging the corners. By default, the system clips any content that draws beyond the bounds. This modifier requests additional space for drawing outside the window’s bounds. Use this space to render extra visual effects that enhance the impact of your app. This content does not receive events, and may be clipped by the system at any time.

The additional margins granted by this modifier are not guaranteed, and the system may update or reduce them. Any time the system updates the current margins, it will update the `windowClippingMargins` value in the environment.

If multiple views request margins, the scene’s preferred margins will be the maximum preferred value for each face. For example, if one view wants a leading margin of `400` and another view a trailing margin of `400`, the scene will request both a leading and trailing margin of `400`. If one view requests a leading margin of `200` and another view a leading margin of `300`, the scene will request `300`.

