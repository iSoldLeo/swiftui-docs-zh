--- 来源：https://developer.apple.com/documentation/SwiftUI/View/volumeBaseplateVisibility(_:)

抓取时间：2025-12-02T16:21:22Z

---

# volumeBaseplateVisibility(_:)

**实例方法**

设置卷轴底板的可见性。底板会在用户看向卷轴底部以及调整卷轴大小时显示。`automatic` 和 `visible` 都会显示底板。`hidden` 则永远不会显示底板。

## 声明

```swift
nonisolated func volumeBaseplateVisibility(_ visibility: Visibility) -> some View

```

## 讨论

底板是一个半透明视图，显示在卷轴底部。

用法：

```swift
WindowGroup() {
    Poker()
        .volumeBaseplateVisibility(.visible)
}
.windowStyle(.volumetric)
```

默认为 `automatic`（可见）。

## 可见性

- **hidden()**：无条件隐藏此视图。

- **labelsHidden()**：隐藏此视图中包含的所有控件的标签。

- **menuIndicator(_:)**：设置此视图中控件的菜单指示器可见性。

- **listRowSeparator(_:edges:)**：设置与此特定行关联的分隔符的显示模式。

- **listSectionSeparator(_:edges:)**：设置是否隐藏与列表部分关联的分隔符。

- **persistentSystemOverlays(_:)**：设置覆盖应用程序的非瞬态系统视图的首选可见性。

- **scrollIndicators(_:axes:)**：设置此视图中滚动指示器的可见性。

- **scrollClipDisabled(_:)**：设置滚动视图是否将其内容裁剪到边界内。

- **tableColumnHeaders(_:)**：控制 `Table` 的列标题视图的可见性。

- **upperLimbVisibility(_:)**：设置呈现 [ImmersiveSpace](../ImmersiveSpace.zh-Hans.md) 场景时用户上肢的首选可见性。


---
source: https://developer.apple.com/documentation/SwiftUI/View/volumeBaseplateVisibility(_:)
crawled: 2025-12-02T16:21:22Z
---

# volumeBaseplateVisibility(_:)

**Instance Method**

Sets the visibility of the baseplate of a volume, which appears when a user looks towards the ‘floor’ of a volume and during resize. Both `automatic` and `visible` will show the baseplate. `hidden` will never show it.

## Declaration

```swift
nonisolated func volumeBaseplateVisibility(_ visibility: Visibility) -> some View

```

## Discussion

The baseplate is a semi-transparent view that appears on the ‘floor’ of a volume.

Usage:

```swift
WindowGroup() {
    Poker()
        .volumeBaseplateVisibility(.visible)
}
.windowStyle(.volumetric)
```

Defaults to `automatic` (visible).

## Visibility

- **hidden()**: Hides this view unconditionally.
- **labelsHidden()**: Hides the labels of any controls contained within this view.
- **menuIndicator(_:)**: Sets the menu indicator visibility for controls within this view.
- **listRowSeparator(_:edges:)**: Sets the display mode for the separator associated with this specific row.
- **listSectionSeparator(_:edges:)**: Sets whether to hide the separator associated with a list section.
- **persistentSystemOverlays(_:)**: Sets the preferred visibility of the non-transient system views overlaying the app.
- **scrollIndicators(_:axes:)**: Sets the visibility of scroll indicators within this view.
- **scrollClipDisabled(_:)**: Sets whether a scroll view clips its content to its bounds.
- **tableColumnHeaders(_:)**: Controls the visibility of a `Table`’s column header views.
- **upperLimbVisibility(_:)**: Sets the preferred visibility of the user’s upper limbs, while an [ImmersiveSpace](../ImmersiveSpace.zh-Hans.md) scene is presented.

