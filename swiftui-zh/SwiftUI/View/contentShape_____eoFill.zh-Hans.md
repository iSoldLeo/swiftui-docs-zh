--- 来源：https://developer.apple.com/documentation/SwiftUI/View/contentShape(_:_:eoFill:)

抓取时间：2025-12-02T17:42:18Z

---

# contentShape(_:_:eoFill:)

**实例方法**

设置此视图的内容形状。

## 声明

```swift
nonisolated func contentShape<S>(_ kind: ContentShapeKinds, _ shape: S, eoFill: Bool = false) -> some View where S : Shape

```

## 参数

- **kind**：要应用于此内容形状的种类。

- **shape**：要使用的形状。

- **eoFill**：一个布尔值，指示是否使用奇偶数绕数规则解释形状。

## 返回值

一个使用指定种类的给定形状的视图。

## 讨论

内容形状用途广泛。您可以通过在 `kind` 中指定内容形状来控制其类型。以下示例设置视图的焦点环形状，而不影响其用于命中测试的形状：

```swift
MyFocusableView()
    .contentShape(.focusEffect, Circle())
```

您可以将多种内容形状应用于同一视图。例如，同时应用 [interaction](../ContentShapeKinds/interaction.zh-Hans.md) 形状和 [focusEffect](../ContentShapeKinds/focusEffect.zh-Hans.md) 形状，即可同时设置视图的命中测试形状和焦点环形状。

## 上下文菜单和拖拽预览

您可以使用相关的内容形状类型（例如 [dragPreview](../ContentShapeKinds/dragPreview.zh-Hans.md) 和 [contextMenuPreview](../ContentShapeKinds/contextMenuPreview.zh-Hans.md)）来控制系统显示的上下文菜单或拖拽预览。

以下示例创建了一个由 [Image](../Image.zh-Hans.md) 和 [Text](../Text.zh-Hans.md) 组成的 [VStack](../VStack.zh-Hans.md)，该视图包含一个带有自定义内容形状的上下文菜单：

```swift
VStack {
    Image("turtlerock")
        .contentShape(.contextMenuPreview,
                      RoundedRectangle(cornerRadius: 10))
    Text("Turtle Rock")
}
.contextMenu {
    Button {
        // Add this item to a list of favorites.
    } label: {
        Label("Add to Favorites", systemImage: "heart")
    }
}
```

当用户在 iOS 或 iPadOS 中使用长按等操作激活上下文菜单时，系统会使用 [Image](../Image.zh-Hans.md) 作为上下文菜单的预览，并应用请求的圆角半径。

内容形状还支持应用修饰符，例如 [inset(by:)](../InsettableShape/inset_by.zh-Hans.md) 来添加内边距。

## 控制命中测试

- **allowsTightening(_:)**：设置此视图中的文本是否可以在必要时压缩字符间距以适应一行。

- **contentShape(_:eoFill:)**：定义用于命中测试的内容形状。

- **ContentShapeKinds**：视图内容形状的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/View/contentShape(_:_:eoFill:)
crawled: 2025-12-02T17:42:18Z
---

# contentShape(_:_:eoFill:)

**Instance Method**

Sets the content shape for this view.

## Declaration

```swift
nonisolated func contentShape<S>(_ kind: ContentShapeKinds, _ shape: S, eoFill: Bool = false) -> some View where S : Shape

```

## Parameters

- **kind**: The kinds to apply to this content shape.
- **shape**: The shape to use.
- **eoFill**: A Boolean that indicates whether the shape is interpreted with the even-odd winding number rule.

## Return Value

A view that uses the given shape for the specified kind.

## Discussion

The content shape has a variety of uses. You can control the kind of the content shape by specifying one in `kind`. The following example sets the focus ring shape of the view, without affecting its shape for hit-testing:

```swift
MyFocusableView()
    .contentShape(.focusEffect, Circle())
```

You can apply multiple kinds of content shapes to the same view. For example, apply a [interaction](../ContentShapeKinds/interaction.zh-Hans.md) shape and [focusEffect](../ContentShapeKinds/focusEffect.zh-Hans.md) shape together to set both the hit-testing shape and focus ring shape on a view.

## Context Menu & Drag Previews

You can control the preview shown by the system for context menus or drags using the relevant content shape kind, like [dragPreview](../ContentShapeKinds/dragPreview.zh-Hans.md) and [contextMenuPreview](../ContentShapeKinds/contextMenuPreview.zh-Hans.md).

The following example creates a [VStack](../VStack.zh-Hans.md) of an [Image](../Image.zh-Hans.md) and [Text](../Text.zh-Hans.md) that has a context menu with a custom content shape:

```swift
VStack {
    Image("turtlerock")
        .contentShape(.contextMenuPreview,
                      RoundedRectangle(cornerRadius: 10))
    Text("Turtle Rock")
}
.contextMenu {
    Button {
        // Add this item to a list of favorites.
    } label: {
        Label("Add to Favorites", systemImage: "heart")
    }
}
```

When someone activates the context menu with an action like touch and hold in iOS or iPadOS, the system uses the [Image](../Image.zh-Hans.md) as the preview for the context menu, applying the requested corner radius.

The content shape also supports applying modifiers such as [inset(by:)](../InsettableShape/inset_by.zh-Hans.md) to add padding.



## Controlling hit testing

- **allowsTightening(_:)**: Sets whether text in this view can compress the space between characters when necessary to fit text in a line.
- **contentShape(_:eoFill:)**: Defines the content shape for hit testing.
- **ContentShapeKinds**: A kind for the content shape of a view.

