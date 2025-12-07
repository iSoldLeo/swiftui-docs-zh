--- 来源：https://developer.apple.com/documentation/SwiftUI/View/mask(_:)

抓取时间：2025-12-01T10:24:52Z

---

# mask(_:)

**实例方法**

使用给定视图的 alpha 通道遮罩当前视图。

## 声明

```swift
nonisolated func mask<Mask>(_ mask: Mask) -> some View where Mask : View

```

## 参数

- **mask**：渲染系统会将该视图的 alpha 值应用到当前视图。

## 说明

当需要将另一个视图的 alpha（不透明度）值应用到当前视图时，请使用 `mask(_:)`。

此示例展示了一个被不透明度为 10% 的矩形遮罩的图像：

```swift
Image(systemName: "envelope.badge.fill")
    .foregroundColor(Color.blue)
    .font(.system(size: 128, weight: .regular))
    .mask(Rectangle().opacity(0.1))
```

## 图形和渲染修改器

- **accentColor(_:)**：设置此视图及其包含的视图的强调色。

- **animation(_:)**：将指定的动画应用于此视图中所有可动画的值。

- **cornerRadius(_:antialiased:)**：以指定的圆角半径将此视图裁剪到其边界框。


---
source: https://developer.apple.com/documentation/SwiftUI/View/mask(_:)
crawled: 2025-12-01T10:24:52Z
---

# mask(_:)

**Instance Method**

Masks this view using the alpha channel of the given view.

## Declaration

```swift
nonisolated func mask<Mask>(_ mask: Mask) -> some View where Mask : View

```

## Parameters

- **mask**: The view whose alpha the rendering system applies to the specified view.

## Discussion

Use `mask(_:)` when you want to apply the alpha (opacity) value of another view to the current view.

This example shows an image masked by rectangle with a 10% opacity:

```swift
Image(systemName: "envelope.badge.fill")
    .foregroundColor(Color.blue)
    .font(.system(size: 128, weight: .regular))
    .mask(Rectangle().opacity(0.1))
```



## Graphics and rendering modifiers

- **accentColor(_:)**: Sets the accent color for this view and the views it contains.
- **animation(_:)**: Applies the given animation to all animatable values within this view.
- **cornerRadius(_:antialiased:)**: Clips this view to its bounding frame, with the specified corner radius.

