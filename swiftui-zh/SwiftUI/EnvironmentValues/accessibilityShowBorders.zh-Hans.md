---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/accessibilityShowBorders
抓取时间： 2025-12-03T06:07:38Z
---

# 无障碍显示边框

**实例属性**

是否启用显示边框的系统偏好设置。在 macOS 上，当启用 "增强对比度 "时，此属性为 true。

## 声明

```swift
@backDeployed(before: iOS 26.1, macOS 26.1, tvOS 26.1, watchOS 26.1, visionOS 26.1)
var accessibilityShowBorders: Bool { get }
```

## 讨论

如果此属性的值为 true，则按钮等交互式自定义控件的绘制方式应使其边缘和边界清晰可见。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/accessibilityShowBorders
crawled: 2025-12-03T06:07:38Z
---

# accessibilityShowBorders

**Instance Property**

Whether the system preference for Show Borders is enabled. On macOS this is true when Increased Contrast is enabled.

## Declaration

```swift
@backDeployed(before: iOS 26.1, macOS 26.1, tvOS 26.1, watchOS 26.1, visionOS 26.1)
var accessibilityShowBorders: Bool { get }
```

## Discussion

If this property’s value is true, interactive custom controls such as buttons should be drawn in such a way that their edges and borders are clearly visible.

