--- 来源：https://developer.apple.com/documentation/SwiftUI/View/complicationForeground()

抓取时间：2025-12-01T10:24:39Z

---

# complicationForeground()

**实例方法**

将此视图提升为复杂功能中的前景。

## 声明

```swift
@MainActor @preconcurrency func complicationForeground() -> some View

```

## 返回值

位于复杂功能前景的视图。

## 说明

前景视图会与其他前景视图一起着色。前景和背景图层的颜色由表盘决定。

## 外观修饰符

- **colorScheme(_:)**：设置此视图的配色方案。

- **listRowPlatterColor(_:)**：设置当此视图置于列表中时，系统应用于行背景的颜色。

- **background(_:alignment:)**：将指定的视图置于此视图的下方。

- **overlay(_:alignment:)**：将辅助视图置于此视图的上方。

- **foregroundColor(_:)**：设置此视图显示的前景元素的颜色。


---
source: https://developer.apple.com/documentation/SwiftUI/View/complicationForeground()
crawled: 2025-12-01T10:24:39Z
---

# complicationForeground()

**Instance Method**

Promotes this view to the foreground in a complication.

## Declaration

```swift
@MainActor @preconcurrency func complicationForeground() -> some View

```

## Return Value

A view that is in the complication foreground.

## Discussion

A view in the foreground will be tinted alongside other foreground views. The color for both the foreground and background layers is determined by the watch face.

## Appearance modifiers

- **colorScheme(_:)**: Sets this view’s color scheme.
- **listRowPlatterColor(_:)**: Sets the color that the system applies to the row background when this view is placed in a list.
- **background(_:alignment:)**: Layers the given view behind this view.
- **overlay(_:alignment:)**: Layers a secondary view in front of this view.
- **foregroundColor(_:)**: Sets the color of the foreground elements displayed by this view.

