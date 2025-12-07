--- 来源：https://developer.apple.com/documentation/SwiftUI/View/inspectorColumnWidth(_:)

抓取时间：2025-12-02T17:31:00Z

---

# inspectorColumnWidth(_:)

**实例方法**

设置当此视图作为尾随列显示时，包含此视图的检查器的固定首选宽度。

## 声明

```swift
nonisolated func inspectorColumnWidth(_ width: CGFloat) -> some View

```

## 参数

- **width**：当检查器作为尾随列显示时，其首选固定宽度。

## 说明

将此修饰符应用于 [inspector(isPresented:content:)](inspector_isPresented_content.zh-Hans.md) 的内容，以指定尾随列的固定首选宽度。如果需要指定灵活的宽度，请使用 [inspectorColumnWidth(min:ideal:max:)](inspectorColumnWidth_min_ideal_max.zh-Hans.md)。

以下示例展示了一个带有检查器的编辑器界面。当以尾列形式呈现时，检查器的固定宽度为 225 点。该示例还使用了 [interactiveDismissDisabled(_:)](interactiveDismissDisabled.zh-Hans.md) 来防止用户操作（例如拖动分隔线）导致检查器折叠。

```swift
MyEditorView()
    .inspector {
        TextTraitsInspectorView()
            .inspectorColumnWidth(225)
            .interactiveDismissDisabled()
    }
```

## 显示检查器

- **inspector(isPresented:content:)**：在视图层级结构中的指定位置插入检查器。

- **inspectorColumnWidth(min:ideal:max:)**：为尾列呈现的检查器设置一个灵活的首选宽度。


---
source: https://developer.apple.com/documentation/SwiftUI/View/inspectorColumnWidth(_:)
crawled: 2025-12-02T17:31:00Z
---

# inspectorColumnWidth(_:)

**Instance Method**

Sets a fixed, preferred width for the inspector containing this view when presented as a trailing column.

## Declaration

```swift
nonisolated func inspectorColumnWidth(_ width: CGFloat) -> some View

```

## Parameters

- **width**: The preferred fixed width for the inspector if presented as a trailing column.

## Discussion

Apply this modifier on the content of a [inspector(isPresented:content:)](inspector_isPresented_content.zh-Hans.md) to specify a fixed preferred width for the trailing column. Use [inspectorColumnWidth(min:ideal:max:)](inspectorColumnWidth_min_ideal_max.zh-Hans.md) if you need to specify a flexible width.

The following example shows an editor interface with an inspector, which when presented as a trailing-column, has a fixed width of 225 points. The example also uses [interactiveDismissDisabled(_:)](interactiveDismissDisabled.zh-Hans.md) to prevent the inspector from being collapsed by user action like dragging a divider.

```swift
MyEditorView()
    .inspector {
        TextTraitsInspectorView()
            .inspectorColumnWidth(225)
            .interactiveDismissDisabled()
    }
```



## Presenting an inspector

- **inspector(isPresented:content:)**: Inserts an inspector at the applied position in the view hierarchy.
- **inspectorColumnWidth(min:ideal:max:)**: Sets a flexible, preferred width for the inspector in a trailing-column presentation.

