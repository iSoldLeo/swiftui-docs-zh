--- 来源：https://developer.apple.com/documentation/SwiftUI/Images
抓取时间：2025-12-02T16:02:50Z

---

# 图片

**API 集合**

向应用的用户界面添加图片和符号。

## 概述

使用 [Image](Image.zh-Hans.md) 视图显示图片，包括 [doc://com.apple.documentation/design/Human-Interface-Guidelines/sf-symbols]、存储在资源目录中的图片以及存储在磁盘上的图片。

对于需要一定时间才能获取的图片（例如，从网络端点加载图片时），可以使用 [AsyncImage](AsyncImage.zh-Hans.md) 异步加载图片。您可以指示该视图在加载操作期间显示占位符。

有关设计指南，请参阅《人机界面指南》中的 [doc://com.apple.documentation/design/Human-Interface-Guidelines/images]。

## 创建图像

- **Image**：用于显示图像的视图。

## 配置图像

- **调整图像大小以适应可用空间**：通过应用视图修饰符来调整应用用户界面中图像的大小和形状。

- **imageScale(_:)**：根据可用的相对尺寸（包括小、中、大图像尺寸）缩放视图中的图像。

- **imageScale**：此环境中的图像缩放比例。

- **Image.Scale**：应用于矢量图像相对于文本的缩放比例。

- **Image.Orientation**：图像的方向。

- **Image.ResizingMode**：SwiftUI 用于调整图像大小以适应其包含视图的模式。

## 异步加载图像

- **AsyncImage**：异步加载并显示图像的视图。

- **AsyncImagePhase**：异步图像加载操作的当前阶段。

## 设置符号变体

- **symbolVariant(_:)**：使视图中的符号显示特定变体。

- **symbolVariants**：此环境中要使用的符号变体。

- **SymbolVariants**：符号的变体。

## 管理符号效果

- **symbolEffect(_:options:isActive:)**：返回一个添加了符号效果的新视图。

- **symbolEffect(_:options:value:)**：返回一个添加了符号效果的新视图。

- **symbolEffectsRemoved(_:)**：返回一个新视图，该视图继承的符号图像效果将被移除或保持不变。

- **SymbolEffectTransition**：创建一个过渡效果，将“出现”、“消失”、“绘制”或“绘制结束”符号动画应用于插入或移除的视图层级结构中的符号图像。

## 设置符号渲染模式

- **symbolRenderingMode(_:)**：设置此视图中符号图像的渲染模式。

- **symbolRenderingMode**：当前符号渲染模式，或者 `nil` 表示使用当前图像和前景样式作为参数自动选择模式。

- **SymbolRenderingMode**：符号渲染模式。

- **SymbolColorRenderingMode**：符号图像中图层的填充方法。

- **SymbolVariableValueMode**：一种渲染符号图像变量值的方法。

## 从视图渲染图像

- **ImageRenderer**：一个从 SwiftUI 视图创建图像的对象。

## 视图

- **视图基础**：使用视图层级结构定义应用程序的视觉元素。

- **视图配置**：调整层级结构中视图的特性。

- **视图样式**：将内置和自定义的外观和行为应用于不同类型的视图。

- **Animations**：响应状态变化，实现平滑的视觉更新。

- **文本输入和输出**：显示格式化文本并获取用户输入的文本。

- **控件和指示器**：显示值并获取用户选择。

- **菜单和命令**：提供对命令和控件的高效、上下文相关的访问方式。

- **Shapes**：使用颜色、渐变或其他图案描绘并填充内置和自定义形状。

- **绘图和图形**：使用图形效果和自定义绘图增强您的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/Images
crawled: 2025-12-02T16:02:50Z
---

# Images

**API Collection**

Add images and symbols to your app’s user interface.

## Overview

Display images, including [doc://com.apple.documentation/design/Human-Interface-Guidelines/sf-symbols], images that you store in an asset catalog, and images that you store on disk, using an [Image](Image.zh-Hans.md) view.



For images that take time to retrieve — for example, when you load an image from a network endpoint — load the image asynchronously using [AsyncImage](AsyncImage.zh-Hans.md). You can instruct that view to display a placeholder during the load operation.

For design guidance, see [doc://com.apple.documentation/design/Human-Interface-Guidelines/images] in the Human Interface Guidelines.

## Creating an image

- **Image**: A view that displays an image.

## Configuring an image

- **Fitting images into available space**: Adjust the size and shape of images in your app’s user interface by applying view modifiers.
- **imageScale(_:)**: Scales images within the view according to one of the relative sizes available including small, medium, and large images sizes.
- **imageScale**: The image scale for this environment.
- **Image.Scale**: A scale to apply to vector images relative to text.
- **Image.Orientation**: The orientation of an image.
- **Image.ResizingMode**: The modes that SwiftUI uses to resize an image to fit within its containing view.

## Loading images asynchronously

- **AsyncImage**: A view that asynchronously loads and displays an image.
- **AsyncImagePhase**: The current phase of the asynchronous image loading operation.

## Setting a symbol variant

- **symbolVariant(_:)**: Makes symbols within the view show a particular variant.
- **symbolVariants**: The symbol variant to use in this environment.
- **SymbolVariants**: A variant of a symbol.

## Managing symbol effects

- **symbolEffect(_:options:isActive:)**: Returns a new view with a symbol effect added to it.
- **symbolEffect(_:options:value:)**: Returns a new view with a symbol effect added to it.
- **symbolEffectsRemoved(_:)**: Returns a new view with its inherited symbol image effects either removed or left unchanged.
- **SymbolEffectTransition**: Creates a transition that applies the Appear, Disappear, DrawOn or DrawOff symbol animation to symbol images within the inserted or removed view hierarchy.

## Setting symbol rendering modes

- **symbolRenderingMode(_:)**: Sets the rendering mode for symbol images within this view.
- **symbolRenderingMode**: The current symbol rendering mode, or `nil` denoting that the mode is picked automatically using the current image and foreground style as parameters.
- **SymbolRenderingMode**: A symbol rendering mode.
- **SymbolColorRenderingMode**: A method of filling a layer in a symbol image.
- **SymbolVariableValueMode**: A method of rendering the variable value of a symbol image.

## Rendering images from views

- **ImageRenderer**: An object that creates images from SwiftUI views.

## Views

- **View fundamentals**: Define the visual elements of your app using a hierarchy of views.
- **View configuration**: Adjust the characteristics of views in a hierarchy.
- **View styles**: Apply built-in and custom appearances and behaviors to different types of views.
- **Animations**: Create smooth visual updates in response to state changes.
- **Text input and output**: Display formatted text and get text input from the user.
- **Controls and indicators**: Display values and get user selections.
- **Menus and commands**: Provide space-efficient, context-dependent access to commands and controls.
- **Shapes**: Trace and fill built-in and custom shapes with a color, gradient, or other pattern.
- **Drawing and graphics**: Enhance your views with graphical effects and customized drawings.

