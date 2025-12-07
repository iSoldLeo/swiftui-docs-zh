---
来源：https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityDropPoint(_:description:)
抓取时间：2025-11-30T21:31:49Z
---

# accessibilityDropPoint(_:description:)

**实例方法**

辅助技术用于结束拖动交互的点。

## 声明

```swift
nonisolated func accessibilityDropPoint(_ point: UnitPoint, description: LocalizedStringKey) -> ModifiedContent<Content, Modifier>
```

## 讨论

如果需要在提示结束拖动交互时向用户提供说明，请使用此修改器。

```swift
struct FolderView: View {
    var folderName: String

    var body: some View {
        FolderIcon(folderName: folderName)
            .accessibilityDropPoint(.center, description: "Move to \(folderName)")
    }
}
```

默认情况下，如果可访问视图或其子树具有拖放交互，辅助技术将自动显示这些交互。但是，如果存在多个此类交互，则每个拖放都应有一个说明，以消除歧义并提供良好的用户体验。




---
source: https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityDropPoint(_:description:)
crawled: 2025-11-30T21:31:49Z
---

# accessibilityDropPoint(_:description:)

**Instance Method**

The point an assistive technology should use to end a drag interaction.

## Declaration

```swift
nonisolated func accessibilityDropPoint(_ point: UnitPoint, description: LocalizedStringKey) -> ModifiedContent<Content, Modifier>
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



