--- 来源：https://developer.apple.com/documentation/SwiftUI/View/inspectorColumnWidth(min:ideal:max:)

抓取时间：2025-12-02T17:31:00Z

---

# inspectorColumnWidth(min:ideal:max:)

**实例方法**

为带有尾列的视图设置一个灵活的、首选的检查器宽度。

## 声明

```swift
nonisolated func inspectorColumnWidth(min: CGFloat? = nil, ideal: CGFloat, max: CGFloat? = nil) -> some View

```

## 参数

- **min**：尾列检查器的最小允许宽度

- **ideal**：检查器在未进行状态恢复时的初始宽度。`ideal`：当用户双击检查器前缘的分隔线时，会影响 macOS 上检查器的最终宽度。单击分隔线进行重新调整

- **max**：尾部列检查器允许的最大宽度

## 讨论

将此修饰符应用于 [inspector(isPresented:content:)](inspector_isPresented_content.zh-Hans.md) 的内容，以指定列的首选灵活宽度。如果需要指定固定宽度，请使用 [inspectorColumnWidth(_:)](inspectorColumnWidth.zh-Hans.md)。

以下示例显示了一个带有检查器的编辑器界面，当以尾部列的形式显示时，其首选宽度为 225 点，最大宽度为 400 点，最小宽度为 150 点（如果允许，则在 150 点时折叠）。

```swift
MyEditorView()
    .inspector {
        TextTraitsInspectorView()
            .inspectorColumnWidth(min: 150, ideal: 225, max: 400)
    }
```

只有部分平台支持灵活的检查器列。如果您指定的宽度在当前显示环境中不受支持，SwiftUI 可能会使用不同的列宽度。

## 显示检查器

- **inspector(isPresented:content:)**：在视图层次结构中的指定位置插入检查器。

- **inspectorColumnWidth(_:)**：设置当此视图的检查器作为尾随列显示时，其固定的首选宽度。


---
source: https://developer.apple.com/documentation/SwiftUI/View/inspectorColumnWidth(min:ideal:max:)
crawled: 2025-12-02T17:31:00Z
---

# inspectorColumnWidth(min:ideal:max:)

**Instance Method**

Sets a flexible, preferred width for the inspector in a trailing-column presentation.

## Declaration

```swift
nonisolated func inspectorColumnWidth(min: CGFloat? = nil, ideal: CGFloat, max: CGFloat? = nil) -> some View

```

## Parameters

- **min**: The minimum allowed width for the trailing column inspector
- **ideal**: The initial width of the inspector in the absence of state restoration. `ideal` influences the resulting width on macOS when a user double-clicks the divider on the leading edge of the inspector. clicks a divider to readjust
- **max**: The maximum allowed width for the trailing column inspector

## Discussion

Apply this modifier on the content of a [inspector(isPresented:content:)](inspector_isPresented_content.zh-Hans.md) to specify a preferred flexible width for the column. Use [inspectorColumnWidth(_:)](inspectorColumnWidth.zh-Hans.md) if you need to specify a fixed width.

The following example shows an editor interface with an inspector, which when presented as a trailing-column, has a preferred width of 225 points, maximum of 400, and a minimum of 150 at which point it will collapse, if allowed.

```swift
MyEditorView()
    .inspector {
        TextTraitsInspectorView()
            .inspectorColumnWidth(min: 150, ideal: 225, max: 400)
    }
```

Only some platforms enable flexible inspector columns. If you specify a width that the current presentation environment doesn’t support, SwiftUI may use a different width for your column.

## Presenting an inspector

- **inspector(isPresented:content:)**: Inserts an inspector at the applied position in the view hierarchy.
- **inspectorColumnWidth(_:)**: Sets a fixed, preferred width for the inspector containing this view when presented as a trailing column.

