---
来源： https://developer.apple.com/documentation/SwiftUI/Accessible-appearance
抓取时间： 2025-12-02T16:49:08Z
---

# 可访问的外观

**API 集合**

提高应用程序界面内容的易读性。

## 概览

通过放大内容、增强对比度或减少干扰动作，让用户更容易看到内容。



有关设计指导，请参阅《人机界面指南》中 "可访问性 "部分的[doc://com.apple.documentation/design/Human-Interface-Guidelines/accessibility#Text-display]。

### 管理颜色

- **accessibilityIgnoresInvertColors(_:)**：设置此视图是否应忽略系统智能反色设置。
- **accessibilityInvertColors**：是否启用 "反转颜色 "的系统偏好设置。
- **accessibilityDifferentiateWithoutColor**：是否启用了 "无彩色区分 "系统偏好设置。

## 放大内容

- **accessibilityShowsLargeContentViewer()**：添加默认大内容视图，由大内容查看器显示。
- **accessibilityShowsLargeContentViewer(_:)**：添加自定义大型内容查看器显示的大型内容视图。
- **accessibilityLargeContentViewerEnabled**：是否启用大型内容查看器。

## 提高可读性

- **accessibilityShowButtonShapes**：是否启用了 "显示按钮形状 "的系统偏好设置。
- **accessibilityReduceTransparency**：是否启用了 "降低透明度 "的系统偏好设置。
- **legibilityWeight**：应用于文本的字体权重。
- **LegibilityWeight**：辅助功能粗体文字用户设置选项。

## 最小化运动

- **accessibilityDimFlashingLights**：是否开启减少视频内容中闪烁或频闪灯光的设置。此设置还可用于确定播放控制中是否应显示用户界面，以指示即将播放的包含闪烁或频闪灯光的内容。
- **accessibilityPlayAnimatedImages**：是否打开在动画图像中播放动画的设置。当此值为假时，任何包含动画的图像都不会自动播放。
- **accessibilityReduceMotion**：是否启用 "减少动态 "系统偏好设置。

## 使用辅助访问

- **accessibilityAssistiveAccessEnabled**：布尔值，表示是否正在使用辅助访问。
- **AssistiveAccess**：在 iOS 和 iPadOS 上显示适合辅助访问功能的界面的场景。在其他平台上，此场景未使用。

### 辅助功能

- 辅助功能基础**：让每个人（包括残障人士）都能访问您的 SwiftUI 应用程序。
- **可访问控件**：提高应用程序可执行操作的可访问性。
- 无障碍描述**：对界面元素进行描述，帮助人们理解它们所代表的含义。
- **无障碍导航**：让用户能够使用转轮导航到特定的用户界面元素。


---
source: https://developer.apple.com/documentation/SwiftUI/Accessible-appearance
crawled: 2025-12-02T16:49:08Z
---

# Accessible appearance

**API Collection**

Enhance the legibility of content in your app’s interface.

## Overview

Make content easier for people to see by making it larger, giving it greater contrast, or reducing the amount of distracting motion.



For design guidance, see [doc://com.apple.documentation/design/Human-Interface-Guidelines/accessibility#Text-display] in the Accessibility section of the Human Interface Guidelines.

## Managing color

- **accessibilityIgnoresInvertColors(_:)**: Sets whether this view should ignore the system Smart Invert setting.
- **accessibilityInvertColors**: Whether the system preference for Invert Colors is enabled.
- **accessibilityDifferentiateWithoutColor**: Whether the system preference for Differentiate without Color is enabled.

## Enlarging content

- **accessibilityShowsLargeContentViewer()**: Adds a default large content view to be shown by the large content viewer.
- **accessibilityShowsLargeContentViewer(_:)**: Adds a custom large content view to be shown by the large content viewer.
- **accessibilityLargeContentViewerEnabled**: Whether the Large Content Viewer is enabled.

## Improving legibility

- **accessibilityShowButtonShapes**: Whether the system preference for Show Button Shapes is enabled.
- **accessibilityReduceTransparency**: Whether the system preference for Reduce Transparency is enabled.
- **legibilityWeight**: The font weight to apply to text.
- **LegibilityWeight**: The Accessibility Bold Text user setting options.

## Minimizing motion

- **accessibilityDimFlashingLights**: Whether the setting to reduce flashing or strobing lights in video content is on. This setting can also be used to determine if UI in playback controls should be shown to indicate upcoming content that includes flashing or strobing lights.
- **accessibilityPlayAnimatedImages**: Whether the setting for playing animations in an animated image is on. When this value is false, any presented image that contains animation should not play automatically.
- **accessibilityReduceMotion**: Whether the system preference for Reduce Motion is enabled.

## Using assistive access

- **accessibilityAssistiveAccessEnabled**: A Boolean value that indicates whether Assistive Access is in use.
- **AssistiveAccess**: A scene that presents an interface appropriate for Assistive Access on iOS and iPadOS. On other platforms, this scene is unused.

## Accessibility

- **Accessibility fundamentals**: Make your SwiftUI apps accessible to everyone, including people with disabilities.
- **Accessible controls**: Improve access to actions that your app can undertake.
- **Accessible descriptions**: Describe interface elements to help people understand what they represent.
- **Accessible navigation**: Enable users to navigate to specific user interface elements using rotors.

