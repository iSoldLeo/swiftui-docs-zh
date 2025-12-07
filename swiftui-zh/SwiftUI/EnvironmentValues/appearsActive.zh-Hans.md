---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/appearsActive
抓取时间： 2025-12-03T06:07:14Z
---

# appearsActive

**实例属性**

该环境中的视图和样式是否更倾向于使用活动外观而非非活动外观。

## 声明

```swift
@backDeployed(before: macOS 15.0)
var appearsActive: Bool { get set }
```

## 讨论

在 macOS 上，聚焦窗口（也称为 "关键 "窗口）中的视图应显示为活动状态。某些上下文在其他情况下也会显示为活动状态，例如，当窗口不是焦点而是主窗口时，窗口工具栏的内容会显示为活动状态。

视图未显示为活动状态时的典型调整包括

- `Color.accentColor`的使用一般应删除或替换为不饱和样式。
- 边栏中的文字和图像内容应显得暗淡一些。
- 带有破坏性操作的按钮应禁用。
- 列表和表格中的⟦和选区将自动变为灰色

自定义视图、样式和形状样式可使用此功能调整自己的外观：

```swift
struct ProminentPillButtonStyle: ButtonStyle {
    @Environment(\.appearsActive) private var appearsActive

    func makeBody(configuration: Configuration) -> some View {
        configuration.label
            .lineLimit(1)
            .padding(.horizontal, 8)
            .padding(.vertical, 2)
            .frame(minHeight: 20)
            .overlay(Capsule().strokeBorder(.tertiary))
            .background(appearsActive ? Color.accentColor : .clear, in: .capsule)
            .contentShape(.capsule)
    }
}
```

在所有其他平台上，该值始终为 `true`。

对于 UIKit 托管内容，该值与`UITraitCollection.activeAppearance` 相连。

## 显示特性

- **colorScheme**：该环境的配色方案。
- **colorSchemeContrast**：与该环境配色方案相关的对比度。
- **displayScale**： 该环境的显示比例：该环境的显示比例。
- **horizontalSizeClass**：此环境的水平尺寸级别。
- **imageScale**：此环境的图像比例。
- **pixelLength**：屏幕上像素的大小。
- **sidebarRowSize**：侧边栏行的当前大小。
- **verticalSizeClass**：该环境的垂直尺寸类别。
- **immersiveSpaceDisplacement**：当沉浸式空间偏离默认位置时，系统应用于该空间的位移，单位为米。
- **labelsVisibility**：[labelsVisibility(_:)](../View/labelsVisibility.zh-Hans.md)设置的标签可见度。
- **materialActiveAppearance**：材料的活动状态应使用的行为，默认为 `automatic`。
- **TabBarPlacement**：标签视图中标签的位置。
- **toolbarLabelStyle**：应用于工具栏内控件的标签样式。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/appearsActive
crawled: 2025-12-03T06:07:14Z
---

# appearsActive

**Instance Property**

Whether views and styles in this environment should prefer an active appearance over an inactive appearance.

## Declaration

```swift
@backDeployed(before: macOS 15.0)
var appearsActive: Bool { get set }
```

## Discussion

On macOS, views in the focused window (also referred to as the “key” window) should appear active. Some contexts also appear active in other circumstances, such as the contents of a window toolbar appearing active when the window is not focused but is the main window.

Typical adjustments made when a view does not appear active include:

- Uses of `Color.accentColor` should generally be removed or replaced with a desaturated style.
- Text and image content in sidebars should appear dimmer.
- Buttons with destructive actions should appear disabled.
- `ShapeStyle.selection` and selection in list and tables will automatically become a grey color

Custom views, styles, and shape styles can use this to adjust their own appearance:

```swift
struct ProminentPillButtonStyle: ButtonStyle {
    @Environment(\.appearsActive) private var appearsActive

    func makeBody(configuration: Configuration) -> some View {
        configuration.label
            .lineLimit(1)
            .padding(.horizontal, 8)
            .padding(.vertical, 2)
            .frame(minHeight: 20)
            .overlay(Capsule().strokeBorder(.tertiary))
            .background(appearsActive ? Color.accentColor : .clear, in: .capsule)
            .contentShape(.capsule)
    }
}
```

On all other platforms, this value is always `true`.

This is bridged with `UITraitCollection.activeAppearance` for UIKit hosted content.

## Display characteristics

- **colorScheme**: The color scheme of this environment.
- **colorSchemeContrast**: The contrast associated with the color scheme of this environment.
- **displayScale**: The display scale of this environment.
- **horizontalSizeClass**: The horizontal size class of this environment.
- **imageScale**: The image scale for this environment.
- **pixelLength**: The size of a pixel on the screen.
- **sidebarRowSize**: The current size of sidebar rows.
- **verticalSizeClass**: The vertical size class of this environment.
- **immersiveSpaceDisplacement**: The displacement that the system applies to the immersive space when moving the space away from its default position, in meters.
- **labelsVisibility**: The labels visibility set by [labelsVisibility(_:)](../View/labelsVisibility.zh-Hans.md).
- **materialActiveAppearance**: The behavior materials should use for their active state, defaulting to `automatic`.
- **TabBarPlacement**: A placement for tabs in a tab view.
- **toolbarLabelStyle**: The label style to apply to controls within a toolbar.

