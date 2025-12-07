---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/accessibilityEnabled
抓取时间： 2025-12-03T06:07:07Z
---

# 辅助功能已启用

**实例属性**

布尔值，表示用户是否启用了辅助技术。

## 声明

```swift
var accessibilityEnabled: Bool { get set }
```

## 可访问性

- **accessibilityAssistiveAccessEnabled**：布尔值，表示是否正在使用辅助访问功能。
- **accessibilityDimFlashingLights**：视频内容中减少闪烁或频闪灯光的设置是否打开。此设置还可用于确定是否应在播放控制中显示用户界面，以提示即将播放包含闪烁或频闪灯光的内容。
- **accessibilityDifferentiateWithoutColor**：是否启用 "无彩色区分 "系统首选项。
- **accessibilityInvertColors**：是否启用了 "反转颜色 "系统偏好设置。
- **accessibilityLargeContentViewerEnabled**：大型内容查看器是否已启用。
- **accessibilityPlayAnimatedImages**：是否打开在动画图像中播放动画的设置。当此值为假时，任何包含动画的图像都不会自动播放。
- **accessibilityPrefersHeadAnchorAlternative**：系统设置是否已打开，以优先选择头部锚定内容的替代内容。
- **accessibilityQuickActionsEnabled**：布尔值，表示是否启用了快速操作功能。
- **accessibilityReduceMotion**：是否启用了减少运动的系统首选项。
- **accessibilityReduceTransparency**：是否已启用减少透明度的系统偏好设置。
- **accessibilityShowButtonShapes**：是否启用 "减少透明度 "系统偏好设置：是否启用了 "显示按钮形状 "的系统偏好设置。
- **accessibilitySwitchControlEnabled**：布尔值，表示是否正在使用开关控制电机辅助功能。
- **accessibilityVoiceOverEnabled**：一个布尔值，用于指示是否正在使用 VoiceOver 屏幕阅读器。
- **legibilityWeight**：应用于文本的字体权重。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/accessibilityEnabled
crawled: 2025-12-03T06:07:07Z
---

# accessibilityEnabled

**Instance Property**

A Boolean value that indicates whether the user has enabled an assistive technology.

## Declaration

```swift
var accessibilityEnabled: Bool { get set }
```

## Accessibility

- **accessibilityAssistiveAccessEnabled**: A Boolean value that indicates whether Assistive Access is in use.
- **accessibilityDimFlashingLights**: Whether the setting to reduce flashing or strobing lights in video content is on. This setting can also be used to determine if UI in playback controls should be shown to indicate upcoming content that includes flashing or strobing lights.
- **accessibilityDifferentiateWithoutColor**: Whether the system preference for Differentiate without Color is enabled.
- **accessibilityInvertColors**: Whether the system preference for Invert Colors is enabled.
- **accessibilityLargeContentViewerEnabled**: Whether the Large Content Viewer is enabled.
- **accessibilityPlayAnimatedImages**: Whether the setting for playing animations in an animated image is on. When this value is false, any presented image that contains animation should not play automatically.
- **accessibilityPrefersHeadAnchorAlternative**: Whether the system setting to prefer alternatives to head-anchored content is on.
- **accessibilityQuickActionsEnabled**: A Boolean that indicates whether the quick actions feature is enabled.
- **accessibilityReduceMotion**: Whether the system preference for Reduce Motion is enabled.
- **accessibilityReduceTransparency**: Whether the system preference for Reduce Transparency is enabled.
- **accessibilityShowButtonShapes**: Whether the system preference for Show Button Shapes is enabled.
- **accessibilitySwitchControlEnabled**: A Boolean value that indicates whether the Switch Control motor accessibility feature is in use.
- **accessibilityVoiceOverEnabled**: A Boolean value that indicates whether the VoiceOver screen reader is in use.
- **legibilityWeight**: The font weight to apply to text.

