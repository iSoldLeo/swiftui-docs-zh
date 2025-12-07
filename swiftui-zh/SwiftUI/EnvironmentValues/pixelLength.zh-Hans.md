---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/pixelLength
抓取时间： 2025-12-02T17:39:12Z
---

# 像素长度

**实例属性**

屏幕上像素的大小。

## 声明

```swift
var pixelLength: CGFloat { get }
```

## 讨论

该值通常等于 `1` 除以 [displayScale](displayScale.zh-Hans.md)。

## 反应接口特性

- **isLuminanceReduced**：布尔值，表示当前显示屏或环境是否需要降低亮度。
- **displayScale**：该环境的显示比例。
- **horizontalSizeClass**：此环境的水平尺寸级别。
- **verticalSizeClass**：该环境的垂直尺寸级别。
- **UserInterfaceSizeClass**：一组表示视图可用视觉尺寸的值。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/pixelLength
crawled: 2025-12-02T17:39:12Z
---

# pixelLength

**Instance Property**

The size of a pixel on the screen.

## Declaration

```swift
var pixelLength: CGFloat { get }
```

## Discussion

This value is usually equal to `1` divided by [displayScale](displayScale.zh-Hans.md).

## Reacting to interface characteristics

- **isLuminanceReduced**: A Boolean value that indicates whether the display or environment currently requires reduced luminance.
- **displayScale**: The display scale of this environment.
- **horizontalSizeClass**: The horizontal size class of this environment.
- **verticalSizeClass**: The vertical size class of this environment.
- **UserInterfaceSizeClass**: A set of values that indicate the visual size available to the view.

