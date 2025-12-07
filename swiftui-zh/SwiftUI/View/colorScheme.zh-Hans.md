--- 来源：https://developer.apple.com/documentation/SwiftUI/View/colorScheme(_:)

抓取时间：2025-12-03T05:35:28Z

---

# colorScheme(_:)

**实例方法**

设置此视图的配色方案。

## 声明

```swift
nonisolated func colorScheme(_ colorScheme: ColorScheme) -> some View

```

## 参数

- **colorScheme**：此视图的配色方案。

## 返回值

一个设置了此视图配色方案的视图。

## 说明

使用 `colorScheme(_:)` 可以为应用此方法的视图及其任何子视图设置配色方案。

## 外观修饰符

- **listRowPlatterColor(_:)**：设置当此视图置于列表中时，系统应用于行背景的颜色。

- **background(_:alignment:)**：将指定的视图置于此视图的下方。

- **overlay(_:alignment:)**：将辅助视图置于此视图的前方。

- **foregroundColor(_:)**：设置此视图显示的前景元素的颜色。

- **complicationForeground()**：在复杂视图中将此视图提升为前景。


---
source: https://developer.apple.com/documentation/SwiftUI/View/colorScheme(_:)
crawled: 2025-12-03T05:35:28Z
---

# colorScheme(_:)

**Instance Method**

Sets this view’s color scheme.

## Declaration

```swift
nonisolated func colorScheme(_ colorScheme: ColorScheme) -> some View

```

## Parameters

- **colorScheme**: The color scheme for this view.

## Return Value

A view that sets this view’s color scheme.

## Discussion

Use `colorScheme(_:)` to set the color scheme for the view to which you apply it and any subviews.

## Appearance modifiers

- **listRowPlatterColor(_:)**: Sets the color that the system applies to the row background when this view is placed in a list.
- **background(_:alignment:)**: Layers the given view behind this view.
- **overlay(_:alignment:)**: Layers a secondary view in front of this view.
- **foregroundColor(_:)**: Sets the color of the foreground elements displayed by this view.
- **complicationForeground()**: Promotes this view to the foreground in a complication.

