---
来源： https://developer.apple.com/documentation/SwiftUI/Building-Layouts-with-Stack-Views
抓取时间： 2025-12-02T17:38:05Z
---

# 使用堆栈视图构建布局

**Article**

从原始容器视图合成复杂布局。

## 概览

单独来看，[HStack](HStack.zh-Hans.md)、[VStack](VStack.zh-Hans.md) 和 [ZStack](ZStack.zh-Hans.md) 都是简单视图。[HStack](HStack.zh-Hans.md)将视图排成水平线，[VStack](VStack.zh-Hans.md)将视图排成垂直线，[ZStack](ZStack.zh-Hans.md)将视图重叠在一起。



使用默认参数初始化时，堆叠视图会将内容居中对齐，并在每个包含的视图之间插入少量间距。但是，如果将堆栈与视图修改器、[Spacer](Spacer.zh-Hans.md) 和[Divider](Divider.zh-Hans.md) 视图结合起来并进行自定义，就可以创建高度灵活和复杂的布局。

### 规划布局层次

在开始将设计转化为代码时，考虑如何使用各种类型的堆栈视图创建布局。将复杂的设计分解成更小、更简单的片段，然后使用堆栈视图创建。

例如，你可以使用三个堆栈视图来创建这个剖面视图：



一个[ZStack](ZStack.zh-Hans.md)视图包含一个[Image](Image.zh-Hans.md)视图，该视图显示带有半透明[HStack](HStack.zh-Hans.md)的个人资料图片。[HStack](HStack.zh-Hans.md)包含一个[VStack](VStack.zh-Hans.md)，其内部有一对[Text](Text.zh-Hans.md)视图，而[Spacer](Spacer.zh-Hans.md)视图将[VStack](VStack.zh-Hans.md)推到了领先的一侧。

要创建此堆栈视图，请

```swift
struct ProfileView: View {
    var body: some View {
        ZStack(alignment: .bottom) {
            Image("ProfilePicture")
                .resizable()
                .aspectRatio(contentMode: .fit)
            HStack {
                VStack(alignment: .leading) {
                    Text("Rachael Chiseck")
                        .font(.headline)
                    Text("Chief Executive Officer")
                        .font(.subheadline)
                }
                Spacer()
            }
            .padding()
            .foregroundColor(.primary)
            .background(Color.primary
                            .colorInvert()
                            .opacity(0.75))
        }
    }
}
```

### 使用对齐和间隔视图定位视图

使用`alignment` 属性、[Spacer](Spacer.zh-Hans.md) 和 [Divider](Divider.zh-Hans.md) 视图的组合，对齐堆栈视图中包含的任何视图。

在上一个布局示例中，包含两个[Text](Text.zh-Hans.md) 视图的[VStack](VStack.zh-Hans.md) 使用了[leading](HorizontalAlignment/leading.zh-Hans.md) 对齐方式：



`alignment` 属性不会将 [VStack](VStack.zh-Hans.md) 定位在其容器内，而是将视图定位在 [VStack](VStack.zh-Hans.md) 内。

[VStack](VStack.zh-Hans.md)的`alignment`属性仅适用于使用[HorizontalAlignment](HorizontalAlignment.zh-Hans.md)的包含控件的水平对齐方式。同样，[HStack](HStack.zh-Hans.md) 的 `alignment` 属性只能使用 [VerticalAlignment](VerticalAlignment.zh-Hans.md) 控制垂直对齐方式。最后，您可以使用[ZStack](ZStack.zh-Hans.md)沿两个轴对⟦内的视图进行对齐。

使用[Spacer](Spacer.zh-Hans.md)视图可沿着[HStack](HStack.zh-Hans.md)或[VStack](VStack.zh-Hans.md)的主轴对齐视图。间隔器可扩展以填充任何可用空间，并将内容与其他视图或堆叠边缘分开。



[Divider](Divider.zh-Hans.md)视图也会在堆栈的子视图之间添加空间，但插入的空间只够在堆栈的次轴上画一条线。它们不会扩展以填充可用空间。

### 创建自适应布局，而不是显式布局

尽可能定义结构和层次，而不是明确定位视图框架。不要为视图使用明确的高度和宽度，而是让它们扩展以填充可用空间。您创建的自适应布局更容易适应不同的设备尺寸和平台。

通过显式操作[Text](Text.zh-Hans.md) 视图框架，可以创建本文示例布局的两个堆栈视图，而不是三个。虽然输出结果可能看起来一样，但实现它的代码却更加脆弱，在不同尺寸级别的设备上可能无法很好地扩展。

您可能需要通过使用[frame(width:height:alignment:)](View/frame_width_height_alignment.zh-Hans.md) 或 [position(x:y:)](View/position_x_y.zh-Hans.md)等视图修饰符对使用显式调整的布局进行调整，但只有在无法以自适应、灵活的方式实现所需的布局时才会考虑这样做。有关对视图布局进行微调的更多信息，请参阅[Making-Fine-Adjustments-to-a-View-s-Position](Making-Fine-Adjustments-to-a-View-s-Position.zh-Hans.md)。

###以其他方式增加深度

在某些情况下，使用[overlay(_:alignment:)](View/overlay___alignment.zh-Hans.md) 和 [background(_:alignment:)](View/background___alignment.zh-Hans.md)视图修饰符而不是[ZStack](ZStack.zh-Hans.md)，可以增加布局的深度。背景视图修改器会在正在修改的视图后面放置另一个视图，而叠加则会在视图上面放置一个视图。

根据您想要确定最终布局大小的方式，在基于堆栈的方法和视图修改器方法之间进行选择。如果布局中有一个决定布局大小的主要视图，则在该视图上使用 [overlay(_:alignment:)](View/overlay___alignment.zh-Hans.md) 或 [background(_:alignment:)](View/background___alignment.zh-Hans.md) 视图修改器。如果希望最终视图大小来自所有包含视图的集合，请使用 [ZStack](ZStack.zh-Hans.md)。

例如，这段代码会在[Image](Image.zh-Hans.md)视图的基础上叠加`ProfileDetail`视图：

```swift
struct ProfileViewWithOverlay: View {
    var body: some View {
        VStack {
            Image("ProfilePicture")
                .resizable()
                .aspectRatio(contentMode: .fit)
                .overlay(ProfileDetail(), alignment: .bottom)
        }
    }
}

struct ProfileDetail: View {
    var body: some View {
        HStack {
            VStack(alignment: .leading) {
                Text("Rachael Chiseck")
                    .font(.headline)
                Text("Chief Executive Officer")
                    .font(.subheadline)
            }
            Spacer()
        }
        .padding()
        .foregroundColor(.primary)
        .background(Color.primary
                        .colorInvert()
                        .opacity(0.75))
    }
}
```

## 在一个维度中静态排列视图

- **HStack**：以水平线排列子视图的视图。
- **VStack**：按垂直线排列子视图的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/Building-Layouts-with-Stack-Views
crawled: 2025-12-02T17:38:05Z
---

# Building layouts with stack views

**Article**

Compose complex layouts from primitive container views.

## Overview

Individually, [HStack](HStack.zh-Hans.md), [VStack](VStack.zh-Hans.md), and [ZStack](ZStack.zh-Hans.md) are simple views. [HStack](HStack.zh-Hans.md) positions views in a horizontal line, [VStack](VStack.zh-Hans.md) positions them in a vertical line, and [ZStack](ZStack.zh-Hans.md) overlays views on top of one another.



When you initialize them with default parameters, stack views center align their content and insert a small amount of spacing between each contained view. But, when you combine and customize stacks with view modifiers, [Spacer](Spacer.zh-Hans.md), and [Divider](Divider.zh-Hans.md) views, you can create highly flexible and complex layouts.

### Plan your layout hierarchy

Think about a layout in terms of how you might create it using the various types of stack views as you start to translate your design into code. Break down complex designs into smaller, simpler pieces you can build with stack views.

For example, you might build this profile view using three stack views:



A [ZStack](ZStack.zh-Hans.md) contains an [Image](Image.zh-Hans.md) view that displays a profile picture with a semi-transparent [HStack](HStack.zh-Hans.md) overlaid on top. The [HStack](HStack.zh-Hans.md) contains a [VStack](VStack.zh-Hans.md) with a pair of [Text](Text.zh-Hans.md) views inside it, and a [Spacer](Spacer.zh-Hans.md) view pushes the [VStack](VStack.zh-Hans.md) to the leading side.

To create this stack view:

```swift
struct ProfileView: View {
    var body: some View {
        ZStack(alignment: .bottom) {
            Image("ProfilePicture")
                .resizable()
                .aspectRatio(contentMode: .fit)
            HStack {
                VStack(alignment: .leading) {
                    Text("Rachael Chiseck")
                        .font(.headline)
                    Text("Chief Executive Officer")
                        .font(.subheadline)
                }
                Spacer()
            }
            .padding()
            .foregroundColor(.primary)
            .background(Color.primary
                            .colorInvert()
                            .opacity(0.75))
        }
    }
}
```

### Position views with alignment and spacer views

Align any contained views inside a stack view by using a combination of the `alignment` property, [Spacer](Spacer.zh-Hans.md), and [Divider](Divider.zh-Hans.md) views.

In the previous example layout, the [VStack](VStack.zh-Hans.md) that contains the two [Text](Text.zh-Hans.md) views uses the [leading](HorizontalAlignment/leading.zh-Hans.md) alignment:



The `alignment` property doesn’t position the [VStack](VStack.zh-Hans.md) inside its container; instead, it positions the views inside the [VStack](VStack.zh-Hans.md).

The `alignment` property of a [VStack](VStack.zh-Hans.md) only applies to the horizontal alignment of the contained controls using [HorizontalAlignment](HorizontalAlignment.zh-Hans.md). Similarly, the `alignment` property for an [HStack](HStack.zh-Hans.md) only controls the vertical alignment using [VerticalAlignment](VerticalAlignment.zh-Hans.md). Finally, you can align views inside a [ZStack](ZStack.zh-Hans.md) along both axes with [Alignment](Alignment.zh-Hans.md).

Use [Spacer](Spacer.zh-Hans.md) views to align views along the primary axis of an [HStack](HStack.zh-Hans.md) or [VStack](VStack.zh-Hans.md). Spacers expand to fill any available space and push content apart from other views or the edges of the stack.



[Divider](Divider.zh-Hans.md) views also add space in between a stack’s subviews, but only insert enough space to draw a line across the stack’s minor axis. They don’t expand to fill available space.

### Create adaptive layouts instead of explicit layouts

Wherever possible, define structure and hierarchy rather than explicitly positioning view frames. Instead of using explicit heights and widths for views, let them expand to fill available space. Adaptive layouts that you build adapt more easily to different device sizes and platforms.

It is possible to create this article’s example layout with two stack views rather than three, by manipulating the [Text](Text.zh-Hans.md) view frames explicitly. While the output might look the same, the code to implement it is more brittle, and might not scale as well across devices of different size classes.

You may need to make adjustments to a layout that uses explicit adjustments by using view modifiers such as [frame(width:height:alignment:)](View/frame_width_height_alignment.zh-Hans.md) or [position(x:y:)](View/position_x_y.zh-Hans.md), but only consider this when you can’t achieve your desired layout in an adaptive, flexible way. For more information on making fine adjustments to view layout, see [Making-Fine-Adjustments-to-a-View-s-Position](Making-Fine-Adjustments-to-a-View-s-Position.zh-Hans.md).

### Add depth in alternative ways

In some situations it may make sense to add depth to your layout by using the [overlay(_:alignment:)](View/overlay___alignment.zh-Hans.md) and [background(_:alignment:)](View/background___alignment.zh-Hans.md) view modifiers instead of a [ZStack](ZStack.zh-Hans.md). The background view modifier places another view behind the view you’re modifying, and overlay places a view on top of it.

Choose between a stack-based approach and the view modifier approach based on how you want to determine the size of the final layout. If your layout has one dominant view that defines the size of the layout, use the [overlay(_:alignment:)](View/overlay___alignment.zh-Hans.md) or [background(_:alignment:)](View/background___alignment.zh-Hans.md) view modifier on that view. If you want the final view size to come from an aggregation of all the contained views, use a [ZStack](ZStack.zh-Hans.md).

For example, this code overlays a `ProfileDetail` view on top of the [Image](Image.zh-Hans.md) view:

```swift
struct ProfileViewWithOverlay: View {
    var body: some View {
        VStack {
            Image("ProfilePicture")
                .resizable()
                .aspectRatio(contentMode: .fit)
                .overlay(ProfileDetail(), alignment: .bottom)
        }
    }
}

struct ProfileDetail: View {
    var body: some View {
        HStack {
            VStack(alignment: .leading) {
                Text("Rachael Chiseck")
                    .font(.headline)
                Text("Chief Executive Officer")
                    .font(.subheadline)
            }
            Spacer()
        }
        .padding()
        .foregroundColor(.primary)
        .background(Color.primary
                        .colorInvert()
                        .opacity(0.75))
    }
}
```

## Statically arranging views in one dimension

- **HStack**: A view that arranges its subviews in a horizontal line.
- **VStack**: A view that arranges its subviews in a vertical line.

