---
来源： https://developer.apple.com/documentation/SwiftUI/HoverEffect/highlight
抓取时间： 2025-12-03T06:45:26Z
---

# 亮点

**类型属性**

一种效果，可将指针变形为视图后方的一个盘子，并显示一个指示位置的光源。

## 声明

```swift
static let highlight: HoverEffect
```

## 讨论

在 tvOS 上，当视图包含在聚焦视图中时，它会在视图上应用投影效果和镜面高光。它还结合了运动效果，通过调整投影矩阵和镜面偏移产生视差效果。

## 获取悬停效果

- **automatic**：一种尝试自动确定效果的效果。这是默认效果。
- **lift**：指针在视图下滑动并在视图放大时消失并获得阴影的效果。


---
source: https://developer.apple.com/documentation/SwiftUI/HoverEffect/highlight
crawled: 2025-12-03T06:45:26Z
---

# highlight

**Type Property**

An effect  that morphs the pointer into a platter behind the view and shows a light source indicating position.

## Declaration

```swift
static let highlight: HoverEffect
```

## Discussion

On tvOS, it applies a projection effect accompanied with a specular highlight on the view when contained within a focused view. It also incorporates motion effects to produce a parallax effect by adjusting the projection matrix and specular offset.

## Getting hover effects

- **automatic**: An effect  that attempts to determine the effect automatically. This is the default effect.
- **lift**: An effect that slides the pointer under the view and disappears as the view scales up and gains a shadow.

