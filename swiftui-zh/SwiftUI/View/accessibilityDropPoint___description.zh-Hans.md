--- 来源：https://developer.apple.com/documentation/SwiftUI/View/accessibilityDropPoint(_:description:)

抓取时间：2025-11-30T21:29:01Z

---

# accessibilityDropPoint(_:description:)

**实例方法**

辅助技术结束拖放交互时应使用的点。

## 声明

```swift
nonisolated func accessibilityDropPoint(_ point: UnitPoint, description: LocalizedStringKey) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## 讨论

当需要向用户提供结束拖放交互的描述时，请使用此修饰符。

```swift
struct FolderView: View {
    var folderName: String

    var body: some View {
        FolderIcon(folderName: folderName)
            .accessibilityDropPoint(.center, description: "Move to \(folderName)")
    }
}
```

默认情况下，如果辅助视图或其子树包含拖放交互，辅助技术会自动显示这些交互。但是，如果存在多个此类交互，则每个拖放操作都应具有描述，以消除歧义并提供良好的用户体验。

## 使手势操作更易于访问

- **accessibilityActivationPoint(_:)**：元素的激活点是辅助技术用于启动手势的位置。

- **accessibilityActivationPoint(_:isEnabled:)**：元素的激活点是辅助技术用于启动手势的位置。

- **accessibilityDragPoint(_:description:)**：辅助技术应使用此点开始拖拽交互。

- **accessibilityDragPoint(_:description:isEnabled:)**：辅助技术应使用此点开始拖拽交互。

- **accessibilityDropPoint(_:description:isEnabled:)**：辅助技术应使用此点结束拖拽交互。

- **accessibilityDirectTouch(_:options:)**：显式设置此辅助元素是否为直接触摸区域。直接触摸区域会将触摸事件直接传递给应用程序，而不是通过 VoiceOver 等辅助技术处理。该修饰符接受一个可选的 `AccessibilityDirectTouchOptions` 选项集，用于自定义直接触摸区域的功能。

- **accessibilityZoomAction(_:)**：为视图添加辅助功能缩放操作。操作允许 VoiceOver 等辅助技术通过调用该操作与视图进行交互。

- **AccessibilityDirectTouchOptions**：定义视图直接触摸区域功能的选项集。

- **AccessibilityZoomGestureAction**：用户使用 VoiceOver 等辅助技术执行的缩放手势的位置和方向信息。


---
source: https://developer.apple.com/documentation/SwiftUI/View/accessibilityDropPoint(_:description:)
crawled: 2025-11-30T21:29:01Z
---

# accessibilityDropPoint(_:description:)

**Instance Method**

The point an assistive technology should use to end a drag interaction.

## Declaration

```swift
nonisolated func accessibilityDropPoint(_ point: UnitPoint, description: LocalizedStringKey) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## Discussion

Use this modifier when you need to provide a description to users when prompted end a drag interaction.

```swift
struct FolderView: View {
    var folderName: String

    var body: some View {
        FolderIcon(folderName: folderName)
            .accessibilityDropPoint(.center, description: "Move to \(folderName)")
    }
}
```

By default, if an accessible view or its subtree has drag and/or drop interactions, they will be automatically exposed by assistive technologies. However, if there is more than one such interaction, each drag or drop should have a description to disambiguate it and give a good user experience.



## Making gestures accessible

- **accessibilityActivationPoint(_:)**: The activation point for an element is the location assistive technologies use to initiate gestures.
- **accessibilityActivationPoint(_:isEnabled:)**: The activation point for an element is the location assistive technologies use to initiate gestures.
- **accessibilityDragPoint(_:description:)**: The point an assistive technology should use to begin a drag interaction.
- **accessibilityDragPoint(_:description:isEnabled:)**: The point an assistive technology should use to begin a drag interaction.
- **accessibilityDropPoint(_:description:isEnabled:)**: The point an assistive technology should use to end a drag interaction.
- **accessibilityDirectTouch(_:options:)**: Explicitly set whether this accessibility element is a direct touch area. Direct touch areas passthrough touch events to the app rather than being handled through an assistive technology, such as VoiceOver. The modifier accepts an optional `AccessibilityDirectTouchOptions` option set to customize the functionality of the direct touch area.
- **accessibilityZoomAction(_:)**: Adds an accessibility zoom action to the view. Actions allow assistive technologies, such as VoiceOver, to interact with the view by invoking the action.
- **AccessibilityDirectTouchOptions**: An option set that defines the functionality of a view’s direct touch area.
- **AccessibilityZoomGestureAction**: Position and direction information of a zoom gesture that someone performs with an assistive technology like VoiceOver.

