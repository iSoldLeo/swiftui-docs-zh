---
来源：https://developer.apple.com/documentation/SwiftUI/WidgetConfiguration/disfavoredLocations(_:for:)
抓取时间：2025-12-03T06:05:46Z
---

# disfavoredLocations(_:for:)

**实例方法**

为 widget 设置不喜欢的位置。

## 声明

```swift
@MainActor @preconcurrency func disfavoredLocations(_ locations: [WidgetLocation], for families: [WidgetFamily]) -> some WidgetConfiguration

```

## 参数

- **locations**：Widget 不喜欢的位置数组。
- **families**：您要在指定位置标记为不受欢迎的族。

## 讨论

在不同的平台上，小部件可以出现在不同的上下文中。例如，一个小的系统 widget 默认会出现在 iPhone 的主屏幕和今日视图中，以及 iPad 的锁定屏幕上，等等。这让更多人有机会查看 Widget 提供的数据和功能。不过，有些 widget 在某个位置可能无法正常工作。例如，严重依赖高分辨率照片和背景颜色来实现功能的 widget 在锁屏上可能效果不佳，因为系统会在锁屏上对 widget 进行鲜艳的处理。要告诉系统，在特定情况下，部件图库应在部件图库的 "其他 "部分显示部件，请使用`.disfavoredLocations`修饰符。

下面的代码片段告诉系统，对于不受欢迎的 `WidgetLocation/lockScreen` 和 `WidgetLocation/homeScreen` 位置，在部件图库的 "其他 "部分显示小型系统家族部件。

```swift
lockScreenOnlyConfig
    .disfavoredLocations([.lockScreen, .homeScreen], for: [.systemSmall])
```

您可以使用对 `disfavoredLocations(_:families:)` 的后续调用来连接它们，并为不同的家族设置不喜欢的位置：

```swift
widgetConfig
    .disfavoredLocations([.lockScreen, .homeScreen], for: [.systemSmall])
    .disfavoredLocations([.homescreen], for: [.systemMedium])
```

## 设置外观

- **supportedFamilies(_:)**：设置 widget 支持的尺寸。
- **contentMarginsDisabled()**：禁用默认内容边距。
- **containerBackgroundRemovable(_:)**：将 widget 的背景标记为可移动的修改器。


---
source: https://developer.apple.com/documentation/SwiftUI/WidgetConfiguration/disfavoredLocations(_:for:)
crawled: 2025-12-03T06:05:46Z
---

# disfavoredLocations(_:for:)

**Instance Method**

Sets the disfavored locations for a widget.

## Declaration

```swift
@MainActor @preconcurrency func disfavoredLocations(_ locations: [WidgetLocation], for families: [WidgetFamily]) -> some WidgetConfiguration

```

## Parameters

- **locations**: An array of disfavored locations for a widget.
- **families**: The families you want to mark as disfavored in the given locations.

## Discussion

A widget can appear in different contexts on different platforms. For example, a small system widget appears by default on the Home Screen and in Today View on iPhone, on the iPad Lock Screen, and so on. This gives more people opportunity to view data and functionality that your widget provides. However, some widgets may not work well in a location. For example, a widget that heavily relies on high-resolution photos and background colors for its functionality may not work well on the Lock Screen, where the system applies a vibrant treatment to the widget. To tell the system that the widget gallery should show a widget in the “Other” section of the widget gallery for a specific context, use the `.disfavoredLocations` modifier.

The following code snippet tells the system to show the small system family widget in the “Other” section of the widget gallery for the disfavored `WidgetLocation/lockScreen` and `WidgetLocation/homeScreen` locations.

```swift
lockScreenOnlyConfig
    .disfavoredLocations([.lockScreen, .homeScreen], for: [.systemSmall])
```

You can use subsequent calls to `disfavoredLocations(_:families:)` to join them and set disfavored locations for different families:

```swift
widgetConfig
    .disfavoredLocations([.lockScreen, .homeScreen], for: [.systemSmall])
    .disfavoredLocations([.homescreen], for: [.systemMedium])
```

## Setting the appearance

- **supportedFamilies(_:)**: Sets the sizes that a widget supports.
- **contentMarginsDisabled()**: Disable default content margins.
- **containerBackgroundRemovable(_:)**: A modifier that marks the background of a widget as removable.

