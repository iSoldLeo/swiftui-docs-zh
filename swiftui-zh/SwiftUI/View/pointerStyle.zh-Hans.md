--- 来源：https://developer.apple.com/documentation/SwiftUI/View/pointerStyle(_:)

抓取时间：2025-12-02T17:41:55Z

---

# pointerStyle(_:)

**实例方法**

设置指针悬停在视图上时显示的指针样式。

## 声明

```swift
nonisolated func pointerStyle(_ style: PointerStyle?) -> some View

```

## 参数

- **style**：要使用的指针样式。

## 返回值

一个视图，当鼠标悬停在视图上时，该视图会更改指针的样式。

## 说明

有关可用指针样式的列表，请参阅 [PointerStyle](../PointerStyle.zh-Hans.md)。

有关如何选择合适的指针样式的指导，请参阅人机界面指南中的 [doc://com.apple.documentation/design/Human-Interface-Guidelines/pointing-devices]。

在此示例中，指针样式表明在按住 Option 键时可以进行矩形选择：

```swift
enum ToolMode {
    // ...
    case selection
}

struct ImageEditorView: View {
    @State private var toolMode?

    var body: some View {
        ImageCanvasView()
            .pointerStyle(
                toolMode == .selection ? .rectSelection : nil)
            .onModifierKeysChanged { _, modifierKeys in
                if modifierKeys.contains(.option) {
                    toolMode = .selection
                } else {
                    toolMode = nil
                }
            }
    }
}
```

## 修改指针外观

- **PointerStyle**：描述指针（也称为光标）悬停在视图上时的外观样式。

- **pointerVisibility(_:)**：设置指针悬停在视图上时的可见性。


---
source: https://developer.apple.com/documentation/SwiftUI/View/pointerStyle(_:)
crawled: 2025-12-02T17:41:55Z
---

# pointerStyle(_:)

**Instance Method**

Sets the pointer style to display when the pointer is over the view.

## Declaration

```swift
nonisolated func pointerStyle(_ style: PointerStyle?) -> some View

```

## Parameters

- **style**: The pointer style to use.

## Return Value

A view that changes the style of the pointer when hovered.

## Discussion

Refer to [PointerStyle](../PointerStyle.zh-Hans.md) for a list of available pointer styles.

For guidance on choosing an appropriate pointer style, refer to [doc://com.apple.documentation/design/Human-Interface-Guidelines/pointing-devices] in the Human Interface Guidelines.

In this example, the pointer style indicates rectangular selection is possible while the Option modifier key is pressed:

```swift
enum ToolMode {
    // ...
    case selection
}

struct ImageEditorView: View {
    @State private var toolMode?

    var body: some View {
        ImageCanvasView()
            .pointerStyle(
                toolMode == .selection ? .rectSelection : nil)
            .onModifierKeysChanged { _, modifierKeys in
                if modifierKeys.contains(.option) {
                    toolMode = .selection
                } else {
                    toolMode = nil
                }
            }
    }
}
```

## Modifying pointer appearance

- **PointerStyle**: A style describing the appearance of the pointer (also called a cursor) when it’s hovered over a view.
- **pointerVisibility(_:)**: Sets the visibility of the pointer when it’s over the view.

