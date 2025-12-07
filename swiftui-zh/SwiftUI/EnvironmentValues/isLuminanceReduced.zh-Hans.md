---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/isLuminanceReduced
抓取时间： 2025-12-02T17:39:10Z
---

# isLuminanceReduced

**实例属性**

布尔值，表示显示屏或环境当前是否需要降低亮度。

## 声明

```swift
var isLuminanceReduced: Bool { get set }
```

## 讨论

检测到这种情况时，请降低视图的整体亮度。例如，可以将大的填充形状改为描边，并选择亮度较低的颜色：

```swift
@Environment(\.isLuminanceReduced) var isLuminanceReduced

var body: some View {
    if isLuminanceReduced {
        Circle()
            .stroke(Color.gray, lineWidth: 10)
    } else {
        Circle()
            .fill(Color.white)
    }
}
```

除了您所做的更改外，系统还可以调暗显示屏，以达到合适的亮度。通过对 `isLuminanceReduced`作出反应，您可以保持对比度和可读性，同时帮助满足降低亮度的要求。



## 响应界面特性

- **displayScale**：该环境的显示比例。
- **pixelLength**：屏幕上像素的大小。
- **horizontalSizeClass**：该环境的水平尺寸类别。
- **verticalSizeClass**：该环境的垂直尺寸级别。
- **UserInterfaceSizeClass**：一组表示视图可用视觉尺寸的值。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/isLuminanceReduced
crawled: 2025-12-02T17:39:10Z
---

# isLuminanceReduced

**Instance Property**

A Boolean value that indicates whether the display or environment currently requires reduced luminance.

## Declaration

```swift
var isLuminanceReduced: Bool { get set }
```

## Discussion

When you detect this condition, lower the overall brightness of your view. For example, you can change large, filled shapes to be stroked, and choose less bright colors:

```swift
@Environment(\.isLuminanceReduced) var isLuminanceReduced

var body: some View {
    if isLuminanceReduced {
        Circle()
            .stroke(Color.gray, lineWidth: 10)
    } else {
        Circle()
            .fill(Color.white)
    }
}
```

In addition to the changes that you make, the system could also dim the display to achieve a suitable brightness. By reacting to `isLuminanceReduced`, you can preserve contrast and readability while helping to satisfy the reduced brightness requirement.



## Reacting to interface characteristics

- **displayScale**: The display scale of this environment.
- **pixelLength**: The size of a pixel on the screen.
- **horizontalSizeClass**: The horizontal size class of this environment.
- **verticalSizeClass**: The vertical size class of this environment.
- **UserInterfaceSizeClass**: A set of values that indicate the visual size available to the view.

