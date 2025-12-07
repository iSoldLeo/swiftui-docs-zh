--- 来源：https://developer.apple.com/documentation/SwiftUI/CustomHoverEffect/highlight
抓取时间：2025-12-03T06:45:30Z

---

# highlight

**类型属性**

一种悬停效果，使用光源高亮显示视图以指示位置。

## 声明

```swift
static var highlight: HighlightHoverEffect { get }
```

## 讨论

当指针输入时，此效果会将指针变形为视图后方的圆盘，并显示指示位置的光源。

在 tvOS 上，当视图处于聚焦状态时，此效果会应用投影效果，并在视图上显示镜面高光。它还结合了运动效果，通过调整投影矩阵和镜面偏移来产生视差效果。

在 visionOS 上，此效果会根据用户注视或触摸视图的位置应用发光效果。

## 获取内置悬停效果

- **automatic**：基于周围环境的默认悬停效果。

- **empty**：悬停时不进行任何更改的效果。

- **lift**：悬停时指针滑入视图下方，并随着视图放大而消失并添加阴影的效果。


---
source: https://developer.apple.com/documentation/SwiftUI/CustomHoverEffect/highlight
crawled: 2025-12-03T06:45:30Z
---

# highlight

**Type Property**

A hover effect that highlights views using a light source to indicate position.

## Declaration

```swift
static var highlight: HighlightHoverEffect { get }
```

## Discussion

For pointer input this effect morphs the pointer into a platter behind the view and shows a light source indicating position.

On tvOS it applies a projection effect accompanied with a specular highlight on the view when contained within a focused view. It also incorporates motion effects to produce a parallax effect by adjusting the projection matrix and specular offset.

On visionOS this effect applies a glow effect based on where the user is looking or touching the view.

## Getting built-in hover effects

- **automatic**: The default hover effect based on the surrounding context.
- **empty**: An effect that applies no changes when hovered.
- **lift**: A hover effect that slides the pointer under the view and disappears as the view scales up and gains a shadow.

