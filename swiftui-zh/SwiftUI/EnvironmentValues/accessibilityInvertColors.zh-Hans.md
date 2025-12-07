---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/accessibilityInvertColors
抓取时间：2025-12-02T17:43:37Z
---

# 可访问性反转颜色

**实例属性**

是否启用了反转颜色的系统偏好设置。

## 声明

```swift
var accessibilityInvertColors: Bool { get }
```

## 讨论

如果此属性的值为 true，则显示将反转。在这种情况下，可能需要调整 UI 绘图，以便在倒置时以最佳方式显示。

## 管理颜色

- **accessibilityIgnoresInvertColors(_:)**：设置此视图是否应忽略系统智能反转设置。
- **accessibilityDifferentiateWithoutColor**：是否启用系统首选项 "无彩色区分"。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/accessibilityInvertColors
crawled: 2025-12-02T17:43:37Z
---

# accessibilityInvertColors

**Instance Property**

Whether the system preference for Invert Colors is enabled.

## Declaration

```swift
var accessibilityInvertColors: Bool { get }
```

## Discussion

If this property’s value is true then the display will be inverted. In these cases it may be needed for UI drawing to be adjusted to in order to display optimally when inverted.

## Managing color

- **accessibilityIgnoresInvertColors(_:)**: Sets whether this view should ignore the system Smart Invert setting.
- **accessibilityDifferentiateWithoutColor**: Whether the system preference for Differentiate without Color is enabled.

