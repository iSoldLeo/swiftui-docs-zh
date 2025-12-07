---
来源：https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityDragPoint(_:description:isEnabled:)
抓取时间： 2025-11-30T21:31:48Z
---

# accessibilityDragPoint(_:description:isEnabled:)

**实例方法**

辅助技术用于开始拖动交互的点。

## 声明

```swift
nonisolated func accessibilityDragPoint(_ point: UnitPoint, description: LocalizedStringKey, isEnabled: Bool) -> ModifiedContent<Content, Modifier>
```

## 参数

- **point**：辅助技术开始拖动交互的时间点。
- **description**：拖动交互的描述。
- **isEnabled**：如果为 true，则应用无障碍拖动点；否则无障碍拖动点保持不变。

## 讨论

如果需要在提示开始拖动交互时向用户提供说明，请使用此修改器。

```swift
struct FileView: View {
    var filename: String

    var body: some View {
        FileIcon(filename: filename)
            .accessibilityDragPoint(
                .center, description: Text("Move \(filename)"))
    }
}
```

默认情况下，如果可访问视图或其子树具有拖放交互，辅助技术将自动显示这些交互。但是，如果存在多个此类交互，则每个拖放都应有一个说明，以消除歧义并提供良好的用户体验。




---
source: https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityDragPoint(_:description:isEnabled:)
crawled: 2025-11-30T21:31:48Z
---

# accessibilityDragPoint(_:description:isEnabled:)

**Instance Method**

The point an assistive technology should use to begin a drag interaction.

## Declaration

```swift
nonisolated func accessibilityDragPoint(_ point: UnitPoint, description: LocalizedStringKey, isEnabled: Bool) -> ModifiedContent<Content, Modifier>
```

## Parameters

- **point**: The point the assistive technology will begin a drag interaction.
- **description**: The description of the drag interaction.
- **isEnabled**: If true the accessibility drag point is applied; otherwise the accessibility drag point is unchanged.

## Discussion

Use this modifier when you need to provide a description to users when prompted begin a drag interaction.

```swift
struct FileView: View {
    var filename: String

    var body: some View {
        FileIcon(filename: filename)
            .accessibilityDragPoint(
                .center, description: Text("Move \(filename)"))
    }
}
```

By default, if an accessible view or its subtree has drag and/or drop interactions, they will be automatically exposed by assistive technologies. However, if there is more than one such interaction, each drag or drop should have a description to disambiguate it and give a good user experience.



