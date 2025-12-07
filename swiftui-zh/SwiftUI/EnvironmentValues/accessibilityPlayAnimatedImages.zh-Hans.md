---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/accessibilityPlayAnimatedImages
抓取时间： 2025-12-02T17:43:44Z
---

# 无障碍播放动画图片

**实例属性**

是否打开在动画图像中播放动画的设置。当此值为 false 时，任何包含动画的图像都不会自动播放。

### 声明

```swift
var accessibilityPlayAnimatedImages: Bool { get }
```

## 尽量减少运动

- **accessibilityDimFlashingLights**：是否开启减少视频内容中闪烁或频闪灯光的设置。此设置还可用于确定播放控制中是否应显示用户界面，以提示即将播放包含闪烁或频闪灯光的内容。
- **accessibilityReduceMotion**：是否启用减少运动的系统偏好设置。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/accessibilityPlayAnimatedImages
crawled: 2025-12-02T17:43:44Z
---

# accessibilityPlayAnimatedImages

**Instance Property**

Whether the setting for playing animations in an animated image is on. When this value is false, any presented image that contains animation should not play automatically.

## Declaration

```swift
var accessibilityPlayAnimatedImages: Bool { get }
```

## Minimizing motion

- **accessibilityDimFlashingLights**: Whether the setting to reduce flashing or strobing lights in video content is on. This setting can also be used to determine if UI in playback controls should be shown to indicate upcoming content that includes flashing or strobing lights.
- **accessibilityReduceMotion**: Whether the system preference for Reduce Motion is enabled.

