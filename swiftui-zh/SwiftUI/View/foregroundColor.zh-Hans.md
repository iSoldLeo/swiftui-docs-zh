--- 来源：https://developer.apple.com/documentation/SwiftUI/View/foregroundColor(_:)

抓取时间：2025-12-01T10:24:38Z

---

# foregroundColor(_:)

**实例方法**

设置此视图显示的前景色。

## 声明

```swift
nonisolated func foregroundColor(_ color: Color?) -> some View

```

## 参数

- **color**：显示此视图时使用的前景色。传递 `nil` 可移除任何自定义前景色，并允许系统或容器提供其自身的前景色。如果不存在容器特定的覆盖，则系统使用主色。

## 返回值

使用您提供的前景色的视图。

## 外观修饰符

- **colorScheme(_:)**：设置此视图的配色方案。

- **listRowPlatterColor(_:)**：设置当此视图置于列表中时，系统应用于行背景的颜色。

- **background(_:alignment:)**：将指定的视图置于此视图的下方。

- **overlay(_:alignment:)**：将辅助视图置于此视图的前方。

- **complicationForeground()**：在复杂视图中将此视图提升为前景。


---
source: https://developer.apple.com/documentation/SwiftUI/View/foregroundColor(_:)
crawled: 2025-12-01T10:24:38Z
---

# foregroundColor(_:)

**Instance Method**

Sets the color of the foreground elements displayed by this view.

## Declaration

```swift
nonisolated func foregroundColor(_ color: Color?) -> some View

```

## Parameters

- **color**: The foreground color to use when displaying this view. Pass `nil` to remove any custom foreground color and to allow the system or the container to provide its own foreground color. If a container-specific override doesn’t exist, the system uses the primary color.

## Return Value

A view that uses the foreground color you supply.

## Appearance modifiers

- **colorScheme(_:)**: Sets this view’s color scheme.
- **listRowPlatterColor(_:)**: Sets the color that the system applies to the row background when this view is placed in a list.
- **background(_:alignment:)**: Layers the given view behind this view.
- **overlay(_:alignment:)**: Layers a secondary view in front of this view.
- **complicationForeground()**: Promotes this view to the foreground in a complication.

