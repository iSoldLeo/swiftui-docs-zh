--- 来源：https://developer.apple.com/documentation/SwiftUI/ColorSchemeContrast
抓取时间：2025-12-02T17:32:46Z

---

# ColorSchemeContrast

**Enumeration**

应用前景颜色和背景颜色之间的对比度。

## 声明

```swift
enum ColorSchemeContrast
```

## 概述

读取 [colorSchemeContrast](EnvironmentValues/colorSchemeContrast.zh-Hans.md) 环境值时，您将获得一个对比度值。该值指示当前视图应用的是标准对比度还是增强对比度。SwiftUI 会在对比度发生变化时更新该值，并重绘依赖于该值的视图。例如，以下视图（[Text](Text.zh-Hans.md)）会在用户启用增强对比度时自动更新：

```swift
@Environment(\.colorSchemeContrast) private var colorSchemeContrast

var body: some View {
    Text(colorSchemeContrast == .standard ? "Standard" : "Increased")
}
```

用户可以通过在 macOS 的“系统偏好设置”>“辅助功能”>“显示”中选择“增强对比度”选项，或在 iOS 的“设置”应用中选择“辅助功能”>“显示与文本大小”来设置对比度。您的应用无法覆盖用户的选择。有关在应用中使用颜色和对比度的信息，请参阅《人机界面指南》（[doc://com.apple.documentation/design/Human-Interface-Guidelines/accessibility#Color-and-effects]）。

## 获取对比度选项

- **ColorSchemeContrast.standard**：SwiftUI 会以应用前景颜色和背景颜色之间的标准对比度显示视图。

- **ColorSchemeContrast.increased**：SwiftUI 会以增强的应用前景颜色和背景颜色之间的对比度显示视图。

## 创建配色方案对比度

- **init(_:)**：根据其辅助功能对比度创建对比度。

## 获取配色方案对比度

- **colorSchemeContrast**：与此环境配色方案关联的对比度。

## 符合以下标准

- CaseIterable

- Copyable

- Equatable

- Hashable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/ColorSchemeContrast
crawled: 2025-12-02T17:32:46Z
---

# ColorSchemeContrast

**Enumeration**

The contrast between the app’s foreground and background colors.

## Declaration

```swift
enum ColorSchemeContrast
```

## Overview

You receive a contrast value when you read the [colorSchemeContrast](EnvironmentValues/colorSchemeContrast.zh-Hans.md) environment value. The value tells you if a standard or increased contrast currently applies to the view. SwiftUI updates the value whenever the contrast changes, and redraws views that depend on the value. For example, the following [Text](Text.zh-Hans.md) view automatically updates when the user enables increased contrast:

```swift
@Environment(\.colorSchemeContrast) private var colorSchemeContrast

var body: some View {
    Text(colorSchemeContrast == .standard ? "Standard" : "Increased")
}
```

The user sets the contrast by selecting the Increase Contrast option in Accessibility > Display in System Preferences on macOS, or Accessibility > Display & Text Size in the Settings app on iOS. Your app can’t override the user’s choice. For information about using color and contrast in your app, see [doc://com.apple.documentation/design/Human-Interface-Guidelines/accessibility#Color-and-effects] in the Human Interface Guidelines.

## Getting contrast options

- **ColorSchemeContrast.standard**: SwiftUI displays views with standard contrast between the app’s foreground and background colors.
- **ColorSchemeContrast.increased**: SwiftUI displays views with increased contrast between the app’s foreground and background colors.

## Creating a color scheme contrast

- **init(_:)**: Creates a contrast from its accessibility contrast equivalent.

## Getting the color scheme contrast

- **colorSchemeContrast**: The contrast associated with the color scheme of this environment.

## Conforms To

- CaseIterable
- Copyable
- Equatable
- Hashable
- Sendable
- SendableMetatype

