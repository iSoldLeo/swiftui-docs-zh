---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/accessibilityReduceMotion
抓取时间： 2025-12-02T17:43:45Z
---

# 无障碍减少运动

**实例属性**

是否启用了减少运动的系统偏好设置。

## 声明

```swift
var accessibilityReduceMotion: Bool { get }
```

## 讨论

如果此属性的值为 true，用户界面应避免大型动画，尤其是模拟三维空间的动画。

## 尽量减少运动

- **accessibilityDimFlashingLights**：是否开启减少视频内容中闪烁或频闪灯光的设置。此设置还可用于确定播放控制中是否应显示用户界面，以提示即将播放包含闪烁或频闪灯光的内容。
- **accessibilityPlayAnimatedImages**：是否打开在动画图像中播放动画的设置。当此值为假时，任何包含动画的图像都不会自动播放。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/accessibilityReduceMotion
crawled: 2025-12-02T17:43:45Z
---

# accessibilityReduceMotion

**Instance Property**

Whether the system preference for Reduce Motion is enabled.

## Declaration

```swift
var accessibilityReduceMotion: Bool { get }
```

## Discussion

If this property’s value is true, UI should avoid large animations, especially those that simulate the third dimension.

## Minimizing motion

- **accessibilityDimFlashingLights**: Whether the setting to reduce flashing or strobing lights in video content is on. This setting can also be used to determine if UI in playback controls should be shown to indicate upcoming content that includes flashing or strobing lights.
- **accessibilityPlayAnimatedImages**: Whether the setting for playing animations in an animated image is on. When this value is false, any presented image that contains animation should not play automatically.

