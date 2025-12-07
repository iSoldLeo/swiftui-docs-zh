---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/accessibilityDifferentiateWithoutColor
抓取时间： 2025-12-02T17:43:37Z
---

# 无障碍无色区分

**实例属性**

是否启用了无彩色区分的系统偏好设置。

## 声明

```swift
var accessibilityDifferentiateWithoutColor: Bool { get }
```

## 讨论

如果这是真的，用户界面就不应只用颜色来传达信息，而应使用形状或字形来传达信息。

## 管理颜色

- **accessibilityIgnoresInvertColors(_:)**：设置该视图是否应忽略系统智能反转设置。
- **accessibilityInvertColors**：是否启用 "反转颜色 "的系统首选项。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/accessibilityDifferentiateWithoutColor
crawled: 2025-12-02T17:43:37Z
---

# accessibilityDifferentiateWithoutColor

**Instance Property**

Whether the system preference for Differentiate without Color is enabled.

## Declaration

```swift
var accessibilityDifferentiateWithoutColor: Bool { get }
```

## Discussion

If this is true, UI should not convey information using color alone and instead should use shapes or glyphs to convey information.

## Managing color

- **accessibilityIgnoresInvertColors(_:)**: Sets whether this view should ignore the system Smart Invert setting.
- **accessibilityInvertColors**: Whether the system preference for Invert Colors is enabled.

