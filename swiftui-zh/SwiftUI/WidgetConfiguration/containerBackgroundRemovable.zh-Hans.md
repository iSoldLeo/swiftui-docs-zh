---
来源： https://developer.apple.com/documentation/SwiftUI/WidgetConfiguration/containerBackgroundRemovable(_:)
抓取时间： 2025-12-01T10:54:47Z
---

# containerBackgroundRemovable(_:)

**实例方法**

将 widget 的背景标记为可移动的修改器。

## 声明

```swift
@MainActor @preconcurrency func containerBackgroundRemovable(_ isRemovable: Bool = true) -> some WidgetConfiguration

```

## 参数

- **isRemovable**：如果 `true`，则 widget 支持在偏好无背景的上下文中移除容器背景。如果`false`，系统不会移除背景。

## 返回值

修改后的 widget 配置。

## 讨论

在大多数情况下，应将 widget 的背景容器标记为可移动，以便人们在尽可能多的上下文中放置 widget。如果将背景标记为不可拆卸，那么在需要可拆卸背景的各种上下文中，widget 就会变得不合格。例如，没有可移动背景的小部件不会出现在 iPad 锁定屏幕的部件库中。

如果你将背景标记为不可移动，系统将始终显示 widget 的背景容器。请注意，背景可能会以不同的方式呈现；例如，可能会出现褪色或去饱和度的效果。

此修改器对 iOS 17、watchOS 10 或 macOS 14 之前的操作系统版本没有影响。

## 设置外观

- **supportedFamilies(_:)**：设置 widget 支持的尺寸。
- **contentMarginsDisabled()**：禁用默认内容边距。
- **disfavoredLocations(_:for:)**：为 widget 设置不喜欢的位置。


---
source: https://developer.apple.com/documentation/SwiftUI/WidgetConfiguration/containerBackgroundRemovable(_:)
crawled: 2025-12-01T10:54:47Z
---

# containerBackgroundRemovable(_:)

**Instance Method**

A modifier that marks the background of a widget as removable.

## Declaration

```swift
@MainActor @preconcurrency func containerBackgroundRemovable(_ isRemovable: Bool = true) -> some WidgetConfiguration

```

## Parameters

- **isRemovable**: If `true`, the widget supports removal of the container background in contexts that prefer no backgrounds. If `false`, the system doesn’t remove the background.

## Return Value

A modified widget configuration.

## Discussion

In most cases, mark the background container of a widget as removable to allow people to place the widget in as many contexts as possible. If you mark the background as nonremovable, the widget becomes ineligible in various contexts that require a removable background. For example, a small widget without a removable background doesn’t appear in the widget gallery on the iPad Lock Screen.

If you mark a background as nonremovable, the system always displays the background container of the widget. Note that the background may render differently; for example, it can appear faded or desaturated.

This modifier has no effect on operation system versions prior to iOS 17, watchOS 10, or macOS 14.

## Setting the appearance

- **supportedFamilies(_:)**: Sets the sizes that a widget supports.
- **contentMarginsDisabled()**: Disable default content margins.
- **disfavoredLocations(_:for:)**: Sets the disfavored locations for a widget.

