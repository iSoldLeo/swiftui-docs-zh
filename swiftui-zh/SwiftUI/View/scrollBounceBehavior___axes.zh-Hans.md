--- 来源：https://developer.apple.com/documentation/SwiftUI/View/scrollBounceBehavior(_:axes:)

抓取时间：2025-12-02T17:40:43Z

---

# scrollBounceBehavior(_:axes:)

**实例方法**

配置可滚动视图沿指定轴的回弹行为。

## 声明

```swift
nonisolated func scrollBounceBehavior(_ behavior: ScrollBounceBehavior, axes: Axis.Set = [.vertical]) -> some View

```

## 参数

- **behavior**：应用于已配置视图中所有可滚动视图的回弹行为。使用 [ScrollBounceBehavior](../ScrollBounceBehavior.zh-Hans.md) 值之一。

- **axes**：要应用 `behavior` 的轴集。默认值为 [vertical](../Axis/vertical.zh-Hans.md)。

## 返回值

已配置指定滚动回弹行为的视图。

## 说明

使用此修饰符可以指示可滚动视图在用户滚动到视图内容末尾时是否回弹，并考虑视图及其内容的相对大小。例如，以下 [ScrollView](../ScrollView.zh-Hans.md) 仅在内容足够大以至于需要滚动时才启用回弹行为：

```swift
ScrollView {
    Text("Small")
    Text("Content")
}
.scrollBounceBehavior(.basedOnSize)
```

此修饰符通过 [Environment](../Environment.zh-Hans.md) 传递滚动回弹模式，这意味着该模式会影响修改后的视图层次结构中的所有可滚动视图。为修饰符提供一个轴，以限制该模式影响的可滚动视图类型。例如，以下示例中的所有滚动视图都可以访问模式值，但只有两个嵌套的滚动视图会受到影响，因为只有它们使用水平滚动：

```swift
ScrollView { // Defaults to vertical scrolling.
    ScrollView(.horizontal) {
        ShelfContent()
    }
    ScrollView(.horizontal) {
        ShelfContent()
    }
}
.scrollBounceBehavior(.basedOnSize, axes: .horizontal)
```

您可以使用此修饰符配置任何类型的可滚动视图，包括 [ScrollView](../ScrollView.zh-Hans.md)、[List](../List.zh-Hans.md)、[Table](../Table.zh-Hans.md) 和 [TextEditor](../TextEditor.zh-Hans.md)：

```swift
List {
    Text("Hello")
    Text("World")
}
.scrollBounceBehavior(.basedOnSize)
```

## 配置滚动回弹行为

- **horizontalScrollBounceBehavior**：可滚动视图水平轴的滚动回弹模式。

- **verticalScrollBounceBehavior**：可滚动视图垂直轴的滚动回弹模式。

- **ScrollBounceBehavior**：可滚动视图到达内容末尾时的回弹方式。


---
source: https://developer.apple.com/documentation/SwiftUI/View/scrollBounceBehavior(_:axes:)
crawled: 2025-12-02T17:40:43Z
---

# scrollBounceBehavior(_:axes:)

**Instance Method**

Configures the bounce behavior of scrollable views along the specified axis.

## Declaration

```swift
nonisolated func scrollBounceBehavior(_ behavior: ScrollBounceBehavior, axes: Axis.Set = [.vertical]) -> some View

```

## Parameters

- **behavior**: The bounce behavior to apply to any scrollable views within the configured view. Use one of the [ScrollBounceBehavior](../ScrollBounceBehavior.zh-Hans.md) values.
- **axes**: The set of axes to apply `behavior` to. The default is [vertical](../Axis/vertical.zh-Hans.md).

## Return Value

A view that’s configured with the specified scroll bounce behavior.

## Discussion

Use this modifier to indicate whether scrollable views bounce when people scroll to the end of the view’s content, taking into account the relative sizes of the view and its content. For example, the following [ScrollView](../ScrollView.zh-Hans.md) only enables bounce behavior if its content is large enough to require scrolling:

```swift
ScrollView {
    Text("Small")
    Text("Content")
}
.scrollBounceBehavior(.basedOnSize)
```

The modifier passes the scroll bounce mode through the [Environment](../Environment.zh-Hans.md), which means that the mode affects any scrollable views in the modified view hierarchy. Provide an axis to the modifier to constrain the kinds of scrollable views that the mode affects. For example, all the scroll views in the following example can access the mode value, but only the two nested scroll views are affected, because only they use horizontal scrolling:

```swift
ScrollView { // Defaults to vertical scrolling.
    ScrollView(.horizontal) {
        ShelfContent()
    }
    ScrollView(.horizontal) {
        ShelfContent()
    }
}
.scrollBounceBehavior(.basedOnSize, axes: .horizontal)
```

You can use this modifier to configure any kind of scrollable view, including [ScrollView](../ScrollView.zh-Hans.md), [List](../List.zh-Hans.md), [Table](../Table.zh-Hans.md), and [TextEditor](../TextEditor.zh-Hans.md):

```swift
List {
    Text("Hello")
    Text("World")
}
.scrollBounceBehavior(.basedOnSize)
```

## Configuring scroll bounce behavior

- **horizontalScrollBounceBehavior**: The scroll bounce mode for the horizontal axis of scrollable views.
- **verticalScrollBounceBehavior**: The scroll bounce mode for the vertical axis of scrollable views.
- **ScrollBounceBehavior**: The ways that a scrollable view can bounce when it reaches the end of its content.

