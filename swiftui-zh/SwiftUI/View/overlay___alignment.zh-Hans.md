--- 来源：https://developer.apple.com/documentation/SwiftUI/View/overlay(_:alignment:)

抓取时间：2025-12-01T10:24:37Z

---

# overlay(_:alignment:)

**实例方法**

将一个辅助视图叠加到当前视图的前面。

## 声明

```swift
nonisolated func overlay<Overlay>(_ overlay: Overlay, alignment: Alignment = .center) -> some View where Overlay : View

```

## 参数

- **overlay**：要叠加到当前视图前面的视图。

- **alignment**：`overlay` 相对于当前视图的对齐方式。

## 返回值

一个将 `overlay` 叠加到当前视图前面的视图。

## 讨论

当您将叠加层应用于视图时，原始视图将继续为生成的视图提供布局特性。在以下示例中，心形图像叠加显示在文件夹图像的上方，并与其底部对齐。

```swift
Image(systemName: "folder")
    .font(.system(size: 55, weight: .thin))
    .overlay(Text("❤️"), alignment: .bottom)
```

## 外观修饰符

- **colorScheme(_:)**：设置此视图的配色方案。

- **listRowPlatterColor(_:)**：设置当此视图放置在列表中时，系统应用于行背景的颜色。

- **background(_:alignment:)**：将给定视图置于此视图的下方。

- **foregroundColor(_:)**：设置此视图显示的前景元素的颜色。

- **complicationForeground()**：在复杂视图中将此视图提升为前景。


---
source: https://developer.apple.com/documentation/SwiftUI/View/overlay(_:alignment:)
crawled: 2025-12-01T10:24:37Z
---

# overlay(_:alignment:)

**Instance Method**

Layers a secondary view in front of this view.

## Declaration

```swift
nonisolated func overlay<Overlay>(_ overlay: Overlay, alignment: Alignment = .center) -> some View where Overlay : View

```

## Parameters

- **overlay**: The view to layer in front of this view.
- **alignment**: The alignment for `overlay` in relation to this view.

## Return Value

A view that layers `overlay` in front of the view.

## Discussion

When you apply an overlay to a view, the original view continues to provide the layout characteristics for the resulting view. In the following example, the heart image is shown overlaid in front of, and aligned to the bottom of the folder image.

```swift
Image(systemName: "folder")
    .font(.system(size: 55, weight: .thin))
    .overlay(Text("❤️"), alignment: .bottom)
```



## Appearance modifiers

- **colorScheme(_:)**: Sets this view’s color scheme.
- **listRowPlatterColor(_:)**: Sets the color that the system applies to the row background when this view is placed in a list.
- **background(_:alignment:)**: Layers the given view behind this view.
- **foregroundColor(_:)**: Sets the color of the foreground elements displayed by this view.
- **complicationForeground()**: Promotes this view to the foreground in a complication.

