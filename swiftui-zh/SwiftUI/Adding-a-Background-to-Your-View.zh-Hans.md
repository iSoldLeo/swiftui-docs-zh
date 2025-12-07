--- 来源：https://developer.apple.com/documentation/SwiftUI/Adding-a-Background-to-Your-View

抓取时间：2025-12-02T17:38:12Z

---

# 为视图添加背景

**Article**

在视图后方创建背景，并将其扩展到安全区域内边距之外。

## 概述

您可以使用 [background(_:alignment:)](View/background___alignment.zh-Hans.md) 视图修饰符将视图添加为背景。要在多个视图下方添加背景，或使背景大于现有视图，您可以将视图分层放置在 [ZStack](ZStack.zh-Hans.md) 中，并将要作为背景的视图放置在视图堆栈的底部。您可以指定背景视图忽略安全区域内边距，从而将背景扩展到部分或全部边缘。

### 添加背景

如果您的设计需要背景，可以使用 [background(_:alignment:)](View/background___alignment.zh-Hans.md) 修饰符将其添加到现有视图下方。以下示例使用 [background(_:alignment:)](View/background___alignment.zh-Hans.md) 视图修饰符为垂直堆栈添加渐变：

```swift
let backgroundGradient = LinearGradient(
    colors: [Color.red, Color.blue],
    startPoint: .top, endPoint: .bottom)

struct SignInView: View {
    @State private var name: String = ""

    var body: some View {
        VStack {
            Text("Welcome")
                .font(.title)
            HStack {
                TextField("Your name?", text: $name)
                    .textFieldStyle(.roundedBorder)
                Button(action: {}, label: {
                    Image(systemName: "arrow.right.square")
                        .font(.title)
                })
            }
            .padding()
        }
        .background(backgroundGradient)
    }
}
```

[background(_:alignment:)](View/background___alignment.zh-Hans.md) 视图修饰符会将背景视图的大小限制为与其附加的视图的大小相同：

### 扩展视图下方的背景

要创建比垂直堆栈更大的背景，请使用不同的方法。您可以在 [VStack](VStack.zh-Hans.md) 的内容上方和下方添加 [Spacer](Spacer.zh-Hans.md) 视图来扩展它，但这也会扩展堆栈的大小，可能会改变其布局。要在不改变堆栈大小的情况下添加更大的背景，请将视图嵌套在 [ZStack](ZStack.zh-Hans.md) 中，以便将 [VStack](VStack.zh-Hans.md) 叠加在背景视图之上：

```swift
struct SignInView: View {
    @State private var name: String = ""

    var body: some View {
        ZStack {
            backgroundGradient
            VStack {
                Text("Welcome")
                    .font(.title)
                HStack {
                    TextField("Your name?", text: $name)
                        .textFieldStyle(.roundedBorder)
                    Button(action: {}, label: {
                        Image(systemName: "arrow.right.square")
                            .font(.title)
                    })
                }
                .padding()
            }
        }
    }
}
```

与使用背景视图修饰符不同，深度堆栈中的视图大小是独立的。[Gradient](Gradient.zh-Hans.md) 中的视图会扩展以填充堆栈的可用空间，但默认情况下会避开安全区域的内边距：

有关使用堆栈组合视图的更多信息，请参阅 [Building-Layouts-with-Stack-Views](Building-Layouts-with-Stack-Views.zh-Hans.md)。

### 将背景扩展到安全区域

默认情况下，SwiftUI 会调整视图的大小和位置，以避开系统定义的安全区域，确保系统内容或设备边缘不会遮挡视图。如果您的设计需要背景扩展到屏幕边缘，请使用 [ignoresSafeArea(_:edges:)](View/ignoresSafeArea___edges.zh-Hans.md) 修饰符来覆盖默认设置。

```swift
struct SignInView: View {
    @State private var name: String = ""
    var body: some View {
        ZStack {
            backgroundGradient
            VStack {
                Text("Welcome")
                    .font(.title)
                HStack {
                    TextField("Your name?", text: $name)
                        .textFieldStyle(.roundedBorder)
                    Button(action: {}, label: {
                        Image(systemName: "arrow.right.square")
                            .font(.title)
                    })
                }
                .padding()
            }
        }
        .ignoresSafeArea()
    }
}
```

背景渐变会填充设备的显示区域，并忽略安全区域的内边距。

### 显示键盘时调整视图

您可以通过添加 [ignoresSafeArea(_:edges:)](View/ignoresSafeArea___edges.zh-Hans.md) 修饰符来忽略键盘的安全区域。激活键盘时，垂直堆栈的内容将保持固定，忽略键盘占用的空间：

要使垂直堆栈的内容遵循安全区域并适应键盘，请将修饰符移动到仅应用于背景视图。

```swift
struct SignInView: View {
    @State private var name: String = ""
    var body: some View {
        ZStack {
            backgroundGradient
                .ignoresSafeArea()
            VStack {
                Text("Welcome")
                    .font(.title)
                HStack {
                    TextField("Your name?", text: $name)
                        .textFieldStyle(.roundedBorder)
                    Button(action: {}, label: {
                        Image(systemName: "arrow.right.square")
                            .font(.title)
                    })
                }
                .padding()
            }
        }
    }
}
```

为了适应键盘，SwiftUI 会调整视图的大小和位置。由于背景视图使用了 [ignoresSafeArea(_:edges:)](View/ignoresSafeArea___edges.zh-Hans.md) 修饰符，因此它保持不变。

## 视图分层

- **ZStack**：覆盖其子视图的视图，并在两个轴上对齐它们。

- **zIndex(_:)**：控制重叠视图的显示顺序。

- **background(alignment:content:)**：将您指定的视图置于此视图的下方。

- **background(_:ignoresSafeAreaEdges:)**：将视图的背景设置为指定样式。

- **background(ignoresSafeAreaEdges:)**：将视图的背景设置为默认背景样式。

- **background(_:in:fillStyle:)**：将视图的背景设置为填充指定样式的可插入形状。

- **background(in:fillStyle:)**：将视图的背景设置为填充默认背景样式的可插入形状。

- **overlay(alignment:content:)**：将您指定的视图置于此视图的前方。

- **overlay(_:ignoresSafeAreaEdges:)**：将指定的样式置于此视图的前方。

- **overlay(_:in:fillStyle:)**：将您指定的形状叠加到此视图的前面。

- **backgroundMaterial**：当前视图下方的材质。

- **containerBackground(_:for:)**：使用视图设置外层容器的背景。

- **containerBackground(for:alignment:content:)**：使用视图设置外层容器的背景。

- **ContainerBackgroundPlacement**：容器背景的位置。


---
source: https://developer.apple.com/documentation/SwiftUI/Adding-a-Background-to-Your-View
crawled: 2025-12-02T17:38:12Z
---

# Adding a background to your view

**Article**

Compose a background behind your view and extend it beyond the safe area insets.

## Overview

You can add a view as a background with the [background(_:alignment:)](View/background___alignment.zh-Hans.md) view modifier. To add a background under multiple views, or to have a background larger than an existing view, you can layer the views by placing them within a [ZStack](ZStack.zh-Hans.md), and place the view you want to be in the background at the bottom of the view stack. You can specify that a background view should ignore the safe area insets to extend the background to some or all edges.

### Add a background

If your design calls for a background, you can use the [background(_:alignment:)](View/background___alignment.zh-Hans.md) modifier to add it underneath an existing view. The following example adds a gradient to the vertical stack using the [background(_:alignment:)](View/background___alignment.zh-Hans.md) view modifier:

```swift
let backgroundGradient = LinearGradient(
    colors: [Color.red, Color.blue],
    startPoint: .top, endPoint: .bottom)

struct SignInView: View {
    @State private var name: String = ""

    var body: some View {
        VStack {
            Text("Welcome")
                .font(.title)
            HStack {
                TextField("Your name?", text: $name)
                    .textFieldStyle(.roundedBorder)
                Button(action: {}, label: {
                    Image(systemName: "arrow.right.square")
                        .font(.title)
                })
            }
            .padding()
        }
        .background(backgroundGradient)
    }
}
```

The [background(_:alignment:)](View/background___alignment.zh-Hans.md) view modifier constrains the size of the background view to be the same size as the view to which it’s attached:



### Expand the background underneath your view

To create a background that’s larger than the vertical stack, use a different technique. You could add [Spacer](Spacer.zh-Hans.md) views above and below the content in the [VStack](VStack.zh-Hans.md) to expand it, but that would also expand the size of the stack, possibly changing it’s layout. To add in a larger background without changing the size of the stack, nest the views within a [ZStack](ZStack.zh-Hans.md) to layer the [VStack](VStack.zh-Hans.md) over the background view:

```swift
struct SignInView: View {
    @State private var name: String = ""

    var body: some View {
        ZStack {
            backgroundGradient
            VStack {
                Text("Welcome")
                    .font(.title)
                HStack {
                    TextField("Your name?", text: $name)
                        .textFieldStyle(.roundedBorder)
                    Button(action: {}, label: {
                        Image(systemName: "arrow.right.square")
                            .font(.title)
                    })
                }
                .padding()
            }
        }
    }
}
```

View sizes within a depth stack are independent, unlike when using the background view modifier. The view from [Gradient](Gradient.zh-Hans.md) expands to fill the space available to the stack, but avoids the safe area insets by default:



For more information on usings stacks to combine views, see [Building-Layouts-with-Stack-Views](Building-Layouts-with-Stack-Views.zh-Hans.md).

### Extend the background into the safe areas

By default, SwiftUI sizes and positions views to avoid system defined safe areas to ensure that system content or the edges of the device won’t obstruct your views. If your design calls for the background to extend to the screen edges, use the [ignoresSafeArea(_:edges:)](View/ignoresSafeArea___edges.zh-Hans.md) modifier to override the default.

```swift
struct SignInView: View {
    @State private var name: String = ""
    var body: some View {
        ZStack {
            backgroundGradient
            VStack {
                Text("Welcome")
                    .font(.title)
                HStack {
                    TextField("Your name?", text: $name)
                        .textFieldStyle(.roundedBorder)
                    Button(action: {}, label: {
                        Image(systemName: "arrow.right.square")
                            .font(.title)
                    })
                }
                .padding()
            }
        }
        .ignoresSafeArea()
    }
}
```

The background gradient fills the display area of the device and ignores the safe area insets.



### Adjust views when displaying the keyboard

You can ignore the keyboard’s safe area by adding the [ignoresSafeArea(_:edges:)](View/ignoresSafeArea___edges.zh-Hans.md) modifier. When you activate the keyboard, the content of the vertical stack remains fixed, ignoring the space used by the keyboard:



To get the contents of the vertical stack to respect the safe areas and adjust to the keyboard, move the modifier to only apply to the background view.

```swift
struct SignInView: View {
    @State private var name: String = ""
    var body: some View {
        ZStack {
            backgroundGradient
                .ignoresSafeArea()
            VStack {
                Text("Welcome")
                    .font(.title)
                HStack {
                    TextField("Your name?", text: $name)
                        .textFieldStyle(.roundedBorder)
                    Button(action: {}, label: {
                        Image(systemName: "arrow.right.square")
                            .font(.title)
                    })
                }
                .padding()
            }
        }
    }
}
```

To accommodate the keyboard, SwiftUI resizes and positions your view. Because the background view has the [ignoresSafeArea(_:edges:)](View/ignoresSafeArea___edges.zh-Hans.md) modifier, it remains unchanged.



## Layering views

- **ZStack**: A view that overlays its subviews, aligning them in both axes.
- **zIndex(_:)**: Controls the display order of overlapping views.
- **background(alignment:content:)**: Layers the views that you specify behind this view.
- **background(_:ignoresSafeAreaEdges:)**: Sets the view’s background to a style.
- **background(ignoresSafeAreaEdges:)**: Sets the view’s background to the default background style.
- **background(_:in:fillStyle:)**: Sets the view’s background to an insettable shape filled with a style.
- **background(in:fillStyle:)**: Sets the view’s background to an insettable shape filled with the default background style.
- **overlay(alignment:content:)**: Layers the views that you specify in front of this view.
- **overlay(_:ignoresSafeAreaEdges:)**: Layers the specified style in front of this view.
- **overlay(_:in:fillStyle:)**: Layers a shape that you specify in front of this view.
- **backgroundMaterial**: The material underneath the current view.
- **containerBackground(_:for:)**: Sets the container background of the enclosing container using a view.
- **containerBackground(for:alignment:content:)**: Sets the container background of the enclosing container using a view.
- **ContainerBackgroundPlacement**: The placement of a container background.

