--- 来源：https://developer.apple.com/documentation/SwiftUI/ScrollView
抓取时间：2025-12-02T17:27:46Z

---

# ScrollView

**Structure**

一个可滚动的视图。

## 声明

```swift
struct ScrollView<Content> where Content : View
```

## 概述

滚动视图在可滚动内容区域内显示其内容。当用户执行平台支持的滚动手势时，滚动视图会调整底层内容的可见部分。`ScrollView` 可以水平滚动、垂直滚动或同时进行水平和垂直滚动，但不提供缩放功能。

在以下示例中，`ScrollView` 允许用户滚动浏览包含 100 个 [Text](Text.zh-Hans.md) 视图的 [VStack](VStack.zh-Hans.md)。列表后的图片显示了滚动视图右侧临时可见的滚动条；您可以使用初始化器 `ScrollView` 的 `showsIndicators` 参数禁用它。

```swift
var body: some View {
    ScrollView {
        VStack(alignment: .leading) {
            ForEach(0..<100) {
                Text("Row \($0)")
            }
        }
    }
}
```

### 控制滚动位置

您可以使用视图修饰符 [defaultScrollAnchor(_:)](View/defaultScrollAnchor.zh-Hans.md) 来控制滚动视图的初始滚动位置。

如果滚动视图在其垂直轴上可滚动，则提供值 `UnitPoint/center`` to have the scroll view start in the center of its content when a scroll view is scrollable in both axes.

⟦CB_0003⟧

Or provide an alignment of `UnitPoint/bottom`` 可使滚动视图从其内容的底部开始滚动。

```swift
ScrollView {
    // initially bottom aligned content
}
.defaultScrollAnchor(.bottom)
```

滚动视图初始渲染后，用户可以滚动滚动视图的内容。

要执行程序化滚动，请使用 [ScrollViewReader](ScrollViewReader.zh-Hans.md) 包裹一个或多个滚动视图。

## 创建滚动视图

- **init(_:showsIndicators:content:)**：创建一个新的滚动视图实例，该实例可沿指定轴方向滚动，并在滚动时显示指示器。

- **init(_:content:)**：创建一个新的滚动视图实例，该实例可沿指定轴方向滚动，并在滚动时显示指示器。

## 配置滚动视图

- **content**：滚动视图的内容。

- **axes**：滚动视图的滚动轴。

- **showsIndicators**：一个值，指示滚动视图是否以适合平台的方式显示内容偏移的滚动分量。

## 支持的类型

- **body**：滚动视图的内容和行为。

## 创建滚动视图

- **ScrollViewReader**：通过代理滚动到已知的子视图，提供程序化滚动功能的视图。

- **ScrollViewProxy**：支持对视图层次结构中的可滚动视图进行程序化滚动的代理值。

## 符合以下标准

- View


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollView
crawled: 2025-12-02T17:27:46Z
---

# ScrollView

**Structure**

A scrollable view.

## Declaration

```swift
struct ScrollView<Content> where Content : View
```

## Overview

The scroll view displays its content within the scrollable content region. As the user performs platform-appropriate scroll gestures, the scroll view adjusts what portion of the underlying content is visible. `ScrollView` can scroll horizontally, vertically, or both, but does not provide zooming functionality.

In the following example, a `ScrollView` allows the user to scroll through a [VStack](VStack.zh-Hans.md) containing 100 [Text](Text.zh-Hans.md) views. The image after the listing shows the scroll view’s temporarily visible scrollbar at the right; you can disable it with the `showsIndicators` parameter of the `ScrollView` initializer.

```swift
var body: some View {
    ScrollView {
        VStack(alignment: .leading) {
            ForEach(0..<100) {
                Text("Row \($0)")
            }
        }
    }
}
```



### Controlling Scroll Position

You can influence where a scroll view is initially scrolled by using the [defaultScrollAnchor(_:)](View/defaultScrollAnchor.zh-Hans.md) view modifier.

Provide a value of `UnitPoint/center`` to have the scroll view start in the center of its content when a scroll view is scrollable in both axes.

```swift
ScrollView([.horizontal, .vertical]) {
    // initially centered content
}
.defaultScrollAnchor(.center)
```

Or provide an alignment of `UnitPoint/bottom`` to have the scroll view start at the bottom of its content when a scroll view is scrollable in its vertical axes.

```swift
ScrollView {
    // initially bottom aligned content
}
.defaultScrollAnchor(.bottom)
```

After the scroll view initially renders, the user may scroll the content of the scroll view.

To perform programmatic scrolling, wrap one or more scroll views with a [ScrollViewReader](ScrollViewReader.zh-Hans.md).

## Creating a scroll view

- **init(_:showsIndicators:content:)**: Creates a new instance that’s scrollable in the direction of the given axis and can show indicators while scrolling.
- **init(_:content:)**: Creates a new instance that’s scrollable in the direction of the given axis and can show indicators while scrolling.

## Configuring a scroll view

- **content**: The scroll view’s content.
- **axes**: The scrollable axes of the scroll view.
- **showsIndicators**: A value that indicates whether the scroll view displays the scrollable component of the content offset, in a way that’s suitable for the platform.

## Supporting types

- **body**: The content and behavior of the scroll view.

## Creating a scroll view

- **ScrollViewReader**: A view that provides programmatic scrolling, by working with a proxy to scroll to known child views.
- **ScrollViewProxy**: A proxy value that supports programmatic scrolling of the scrollable views within a view hierarchy.

## Conforms To

- View

