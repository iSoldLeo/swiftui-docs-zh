--- 来源：https://developer.apple.com/documentation/SwiftUI/View/cornerRadius(_:antialiased:)

抓取时间：2025-12-03T05:35:46Z

---

# cornerRadius(_:antialiased:)

**实例方法**

使用此方法将此视图裁剪到其边界框，并指定圆角半径。

## 声明

```swift
nonisolated func cornerRadius(_ radius: CGFloat, antialiased: Bool = true) -> some View

```

## 参数

- **radius**：一个 CGFloat 值，用于指定将视图裁剪到其边界框时使用的圆角半径。

- **antialiased**：一个布尔值，指示渲染系统是否对裁剪矩形的边缘应用平滑处理。

## 返回值

一个使用此视图并指定圆角半径将其裁剪到其边界框的视图。

## 讨论

默认情况下，视图的边界框仅影响其布局，因此超出边界框边缘的内容仍然可见。使用 `cornerRadius(_:antialiased:)` 可以隐藏超出边界框边缘的内容，同时应用圆角半径。

以下代码为文本视图应用了 25 的圆角半径：

```swift
Text("Rounded Corners")
    .frame(width: 175, height: 75)
    .foregroundColor(Color.white)
    .background(Color.black)
    .cornerRadius(25)
```

## 图形和渲染修改器

- **accentColor(_:)**：设置此视图及其包含的视图的强调色。

- **mask(_:)**：使用给定视图的 Alpha 通道遮罩此视图。

- **animation(_:)**：将给定的动画应用于此视图中所有可动画的值。


---
source: https://developer.apple.com/documentation/SwiftUI/View/cornerRadius(_:antialiased:)
crawled: 2025-12-03T05:35:46Z
---

# cornerRadius(_:antialiased:)

**Instance Method**

Clips this view to its bounding frame, with the specified corner radius.

## Declaration

```swift
nonisolated func cornerRadius(_ radius: CGFloat, antialiased: Bool = true) -> some View

```

## Parameters

- **radius**: A CGFloat value that specifies the corner radius to use when clipping the view to its bounding frame.
- **antialiased**: A Boolean value that indicates whether the rendering system applies smoothing to the edges of the clipping rectangle.

## Return Value

A view that clips this view to its bounding frame with the specified corner radius.

## Discussion

By default, a view’s bounding frame only affects its layout, so any content that extends beyond the edges of the frame remains visible. Use `cornerRadius(_:antialiased:)` to hide any content that extends beyond these edges while applying a corner radius.

The following code applies a corner radius of 25 to a text view:

```swift
Text("Rounded Corners")
    .frame(width: 175, height: 75)
    .foregroundColor(Color.white)
    .background(Color.black)
    .cornerRadius(25)
```



## Graphics and rendering modifiers

- **accentColor(_:)**: Sets the accent color for this view and the views it contains.
- **mask(_:)**: Masks this view using the alpha channel of the given view.
- **animation(_:)**: Applies the given animation to all animatable values within this view.

