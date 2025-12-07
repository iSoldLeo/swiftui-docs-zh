--- 来源：https://developer.apple.com/documentation/swiftui/laying-out-a-simple-view

抓取时间：2025-12-05T22:27:42Z

---

# 布局一个简单的视图

**Article**

通过调整视图的大小来创建视图布局。

## 概述

要为视图创建布局，首先要构建子视图的层次结构。然后，使用配置参数和添加视图修饰符（例如影响视图框架和内边距的修饰符）来调整子视图的大小和间距。要了解如何构建布局，请参阅 [Building-Layouts-with-Stack-Views](Building-Layouts-with-Stack-Views.zh-Hans.md)。

### 建立视图层次结构

以下示例创建一个视图来显示来自消息服务的传入消息。该视图使用 [HStack](HStack.zh-Hans.md) 来收集两个视图：一个用于标识发件人，另一个用于提供消息内容。

```swift
struct MessageRow: View {
    let message: Message

    var body: some View {
        HStack {
            ZStack {
                Circle()
                    .fill(Color.yellow)
                Text(message.initials)
            }

            Text(message.content)
        }
    }
}
```

以下 `MessageRow` 视图的屏幕截图包含一个显示其边界的边框。请注意圆圈的尺寸很大，它几乎填满了所有可用空间：

当 SwiftUI 渲染视图层级结构时，它会递归地评估每个子视图：父视图会向其包含的子视图提出一个大小建议，子视图则会返回一个计算出的大小。

`MessageRow` 视图会向其唯一的子视图 [HStack](HStack.zh-Hans.md) 提出一个大小建议，该大小是其父视图提出的完整大小。堆栈会按比例将此空间分配给其子视图，每个子视图之间的间距为系统默认值。这个过程会递归地进行：

- [ZStack](ZStack.zh-Hans.md) 向其子视图 [Circle](Circle.zh-Hans.md) 和 [Text](Text.zh-Hans.md) 提供一个大小建议。

- [Circle](Circle.zh-Hans.md) 会扩展到建议的大小，而 [Text](Text.zh-Hans.md) 则只占用刚好容纳其所包含字符串的空间。

- [ZStack](ZStack.zh-Hans.md) 返回其最大子视图的大小，在本例中为 [Circle](Circle.zh-Hans.md)。

当所有子视图都报告了它们的大小后，父视图会渲染它们。要实际学习 SwiftUI 视图层级结构的工作原理，请参阅“SwiftUI 入门”教程中的 [doc://com.apple.documentation/tutorials/SwiftUI/building-lists-and-navigation] 部分。

### 限制视图大小

在上面的示例中，SwiftUI 内置了一些视图，它们以不同的方式管理大小，包括以下几种视图：

- 会扩展以填充其父视图提供的空间，例如 [Color](Color.zh-Hans.md)、[LinearGradient](LinearGradient.zh-Hans.md) 和 [Circle](Circle.zh-Hans.md)。

- 具有一个理想大小，该大小会根据其内容而变化，例如 [Text](Text.zh-Hans.md) 和容器视图。

- 具有一个固定大小，例如 [Toggle](Toggle.zh-Hans.md) 或 [DatePicker](DatePicker.zh-Hans.md)。

您可以通过添加 frame 修饰符来将视图限制为固定大小。例如，使用 [frame(width:height:alignment:)](View/frame_width_height_alignment.zh-Hans.md) 修饰符将圆的宽度限制为 `40` 点：

```swift
struct MessageRow: View {
    let message: Message

    var body: some View {
        HStack {
            ZStack {
                Circle()
                    .fill(Color.yellow)
                Text(message.initials)
            }
            .frame(width: 40)

            Text(message.content)
        }
    }
}
```

添加 frame 修饰符时，SwiftUI 会包装受影响的视图，实际上是在视图层级结构中添加了一个新视图。

当 SwiftUI 评估这个新的层级结构时，frame 修饰符会通过传递您指定的参数值来固定它所包装的 [ZStack](ZStack.zh-Hans.md) 的宽度。其余的尺寸评估过程与之前相同，其中 [Circle](Circle.zh-Hans.md) 现在会扩展以填充更小的空间，并受到 frame 的 40 点宽度的限制。这使得 [HStack](HStack.zh-Hans.md) 可以为其显示消息文本的子视图提供更多空间。

### 使用对齐方式定位内容

如果您希望圆的顶部与消息内容文本的顶部对齐，可以通过对 [HStack](HStack.zh-Hans.md) 应用对齐方式来优化视图。要将内容在堆栈中垂直定位，请为 [top](VerticalAlignment/top.zh-Hans.md) 指定 `alignment` 参数：

```swift
struct MessageRow: View {
    let message: Message

    var body: some View {
        HStack(alignment: .top) {
            ZStack {
                Circle()
                    .fill(Color.yellow)
                Text(message.initials)
            }
            .frame(width: 40)

            Text(message.content)
        }
    }
}
```

应用对齐方式后，您会得到一个意想不到的结果。视图的顶部似乎没有对齐：

但是，如果您在 Xcode 中选择圆，或者临时为圆添加边框，您会发现视图的顶部实际上是对齐的。有关检查视图大小的更多信息，请参阅 [Inspecting-View-Layout](Inspecting-View-Layout.zh-Hans.md)。

在上一节中，您应用了一个仅具有宽度约束的框架。SwiftUI 绘制了一个受该宽度限制的圆。但由于高度未指定，圆的边框会单独扩展以填充可用高度，即使这额外的空间对渲染的圆没有明显影响。您可以通过添加显式的 `height` 参数来解决此问题：

```swift
struct MessageRow: View {
    let message: Message

    var body: some View {
        HStack(alignment: .top) {
            ZStack {
                Circle()
                    .fill(Color.yellow)
                Text(message.initials)
            }
            .frame(width: 40, height: 40)

            Text(message.content)
        }
    }
}
```

[HStack](HStack.zh-Hans.md) 的内容现在顶部对齐，尽管堆栈本身在 `MessageRow` 视图中居中显示，如显示行边界的边框所示。

### 为视图添加内边距

为避免视图外边缘在视觉上显得拥挤，请添加内边距。这会在指定边缘引入固定量的空间，从而相应地减少视图内容的可用空间。例如，您可以使用 [padding(_:_:)](View/padding.zh-Hans.md) 在 [HStack](HStack.zh-Hans.md) 的 [horizontal](Edge/Set/horizontal.zh-Hans.md) 边缘添加额外空间：

```swift
struct MessageRow: View {
    let message: Message

    var body: some View {
        HStack(alignment: .top) {
            ZStack {
                Circle()
                    .fill(Color.yellow)
                Text(message.initials)
            }
            .frame(width: 40, height: 40)

            Text(message.content)
        }
        .padding([.horizontal])
    }
}
```

内边距修饰符默认使用系统标准间距，但您也可以为内边距修饰符选择不同的值。

## 微调布局

- **检查视图布局**：使用 Xcode 预览或添加临时边框来确定视图的位置和范围。


---
source: https://developer.apple.com/documentation/swiftui/laying-out-a-simple-view
crawled: 2025-12-05T22:27:42Z
---

# Laying out a simple view

**Article**

Create a view layout by adjusting the size of views.

## Overview

To create a layout for a view, start by composing a hierarchy of child views. Then, refine the size and spacing of the child views with configuration parameters, and by adding view modifiers, like those that affect a view’s frame and padding. To review how to compose layouts, see [Building-Layouts-with-Stack-Views](Building-Layouts-with-Stack-Views.zh-Hans.md).

### Establish a view hierarchy

The following example creates a view to display an incoming message from a messaging service. The view uses an [HStack](HStack.zh-Hans.md) to collect a view that identifies the sender and another that provides the content of the message:

```swift
struct MessageRow: View {
    let message: Message

    var body: some View {
        HStack {
            ZStack {
                Circle()
                    .fill(Color.yellow)
                Text(message.initials)
            }

            Text(message.content)
        }
    }
}
```

The following screenshot of a `MessageRow` view includes a border that shows its bounds. Note the large size of the circle, which fills the space available to it:



When SwiftUI renders a view hierarchy, it recursively evaluates each child view: The parent view proposes a size to the child views it contains, and the child views respond with a computed size.



The `MessageRow` view proposes a size to its only child, the [HStack](HStack.zh-Hans.md), which is the full size proposed to it by its own parent. The stack proportionally divides this space between its child views, with system-default spacing between each child. This continues recursively:

- The [ZStack](ZStack.zh-Hans.md) proposes a size to its child views, the [Circle](Circle.zh-Hans.md) and [Text](Text.zh-Hans.md) views.
- The [Circle](Circle.zh-Hans.md) expands up to the size offered, while the [Text](Text.zh-Hans.md) takes just enough space for the string it contains.
- The [ZStack](ZStack.zh-Hans.md) returns the size of its largest child view, in this case the [Circle](Circle.zh-Hans.md).

When all child views have reported their size, the parent view renders them. For a hands-on approach to learning how the SwiftUI view hierarchy works, see the [doc://com.apple.documentation/tutorials/SwiftUI/building-lists-and-navigation] section in the Introducing SwiftUI tutorial.

### Limit the view size

In the example above, SwiftUI has built-in views that manage size in different ways, including views that:

- Expand to fill the space offered by their parent, like [Color](Color.zh-Hans.md), [LinearGradient](LinearGradient.zh-Hans.md), and [Circle](Circle.zh-Hans.md).
- Have an ideal size that varies according to their contents, like [Text](Text.zh-Hans.md) and the container views.
- Have an ideal size that never varies, like [Toggle](Toggle.zh-Hans.md) or [DatePicker](DatePicker.zh-Hans.md).

You can constrain a view to a fixed size by adding a frame modifier. For example, use the [frame(width:height:alignment:)](View/frame_width_height_alignment.zh-Hans.md) modifier to limit the width the circle to `40` points:

```swift
struct MessageRow: View {
    let message: Message

    var body: some View {
        HStack {
            ZStack {
                Circle()
                    .fill(Color.yellow)
                Text(message.initials)
            }
            .frame(width: 40)

            Text(message.content)
        }
    }
}
```

When you add a frame modifier, SwiftUI wraps the affected view, effectively adding a new view to the view hierarchy.



When SwiftUI evaluates this new hierarchy, the frame modifier fixes the width of the [ZStack](ZStack.zh-Hans.md) that it wraps by passing along the value you specified as its parameter. The remainder of the size evaluation proceeds as before, where the [Circle](Circle.zh-Hans.md) now expands to fill a smaller space, constrained by the frame’s 40 point width. This enables the [HStack](HStack.zh-Hans.md) to provide more space to its other child, which displays the message text.



### Position content with alignment

If you want the top of the circle aligned with the top of the message content text, you can refine the view by applying an alignment to the [HStack](HStack.zh-Hans.md). To position the content vertically within the stack, specify the `alignment` parameter to [top](VerticalAlignment/top.zh-Hans.md):

```swift
struct MessageRow: View {
    let message: Message

    var body: some View {
        HStack(alignment: .top) {
            ZStack {
                Circle()
                    .fill(Color.yellow)
                Text(message.initials)
            }
            .frame(width: 40)

            Text(message.content)
        }
    }
}
```

With the alignment applied, you get an unexpected result. The tops of the views don’t appear to align:



However, if you select the circle in Xcode, or temporarily add a border to the circle, you can see the tops of the views do in fact align. For more information on inspecting the size of a view, see [Inspecting-View-Layout](Inspecting-View-Layout.zh-Hans.md).



In the previous section, you applied a frame with only a width constraint. SwiftUI drew a circle limited by that width. But because the height was left unspecified, the circle’s frame separately expanded to fill the available height, even though that extra space had no visible impact on the rendered circle. You can resolve this problem by adding an explicit `height` parameter:

```swift
struct MessageRow: View {
    let message: Message

    var body: some View {
        HStack(alignment: .top) {
            ZStack {
                Circle()
                    .fill(Color.yellow)
                Text(message.initials)
            }
            .frame(width: 40, height: 40)

            Text(message.content)
        }
    }
}
```

The contents of the [HStack](HStack.zh-Hans.md) are now top aligned, although the stack itself is centered in the `MessageRow` view as shown by the border displaying the row’s boundaries.



### Add padding to the view

To avoid visually crowding the outer edges of a view, add padding. This introduces a fixed amount of space along the specified edges, reducing the space available for the contents of the view by a corresponding amount. For example, you can use [padding(_:_:)](View/padding.zh-Hans.md) to add extra space along the [horizontal](Edge/Set/horizontal.zh-Hans.md) edges of the [HStack](HStack.zh-Hans.md):

```swift
struct MessageRow: View {
    let message: Message

    var body: some View {
        HStack(alignment: .top) {
            ZStack {
                Circle()
                    .fill(Color.yellow)
                Text(message.initials)
            }
            .frame(width: 40, height: 40)

            Text(message.content)
        }
        .padding([.horizontal])
    }
}
```

The padding modifier defaults to system-standard spacing, although you can alternatively choose different values for the padding modifier. 

## Finetuning a layout

- **Inspecting view layout**: Determine the position and extent of a view using Xcode previews or by adding temporary borders.

