---
来源： https://developer.apple.com/documentation/SwiftUI/ShadowStyle/drop(color:radius:x:y:)
抓取时间：2025-12-01T11:14:47Z
---

# drop(color:radius:x:y:)

**类型方法**

创建自定义阴影样式。

## 声明

```swift
static func drop(color: Color = .init(.sRGBLinear, white: 0, opacity: 0.33), radius: CGFloat, x: CGFloat = 0, y: CGFloat = 0) -> ShadowStyle
```

## 参数

- **color**：阴影的颜色。
- **radius**：阴影的大小。
- **x**：水平偏移量，用于将阴影相对于此视图定位。
- **y**：垂直偏移量，用于将阴影相对于此视图定位。

## 返回值

新的阴影样式。

## 讨论

阴影通过模糊、着色和偏移每个像素的 alpha 值，在源内容后面绘制。

## 获取阴影样式

- **inner(color:radius:x:y:)**：创建自定义的内部阴影样式。


---
source: https://developer.apple.com/documentation/SwiftUI/ShadowStyle/drop(color:radius:x:y:)
crawled: 2025-12-01T11:14:47Z
---

# drop(color:radius:x:y:)

**Type Method**

Creates a custom drop shadow style.

## Declaration

```swift
static func drop(color: Color = .init(.sRGBLinear, white: 0, opacity: 0.33), radius: CGFloat, x: CGFloat = 0, y: CGFloat = 0) -> ShadowStyle
```

## Parameters

- **color**: The shadow’s color.
- **radius**: The shadow’s size.
- **x**: A horizontal offset you use to position the shadow relative to this view.
- **y**: A vertical offset you use to position the shadow relative to this view.

## Return Value

A new shadow style.

## Discussion

Drop shadows draw behind the source content by blurring, tinting and offsetting its per-pixel alpha values.

## Getting shadow styles

- **inner(color:radius:x:y:)**: Creates a custom inner shadow style.

