---
来源： https://developer.apple.com/documentation/SwiftUI/Shapes
抓取时间： 2025-12-02T16:02:52Z
---

# 形状

**API 集合**

使用颜色、渐变或其他图案对内置和自定义形状进行描边和填充。

### 概览

绘制圆形和矩形等形状，以及定义自己设计形状的自定义路径。在形状的前景、背景和轮廓上应用样式，包括环境感知颜色、丰富的渐变和材质效果。



如果你需要即时模式绘图的效率或灵活性，例如创建粒子效果，请使用[Canvas](Canvas.zh-Hans.md)视图。

## 创建矩形

- **Rectangle**：在包含它的视图的框架内对齐的矩形。
- **RoundedRectangle**：带圆角的矩形，在包含它的视图的边框内对齐。
- **RoundedCornerStyle**：定义圆角矩形的边角形状。
- **RoundedRectangularShape**：[InsettableShape](InsettableShape.zh-Hans.md)的协议，描述圆角矩形的形状。
- **RoundedRectangularShapeCorners**：描述[RoundedRectangularShape](RoundedRectangularShape.zh-Hans.md) 角样式的类型。
- **UnevenRoundedRectangle**：带有不同值的圆角矩形，在包含它的视图框架内对齐。
- **RectangleCornerRadii**：描述圆角矩形的边角半径值，边角不平整。
- **RectangleCornerInsets**：矩形边角的嵌入尺寸。
- **ConcentricRectangle**：由当前容器形状的同心版本替换的形状。如果容器形状是带有四个角的矩形派生形状，该形状可以选择单独尊重角。

## 创建圆形形状

- **Circle**：以包含它的视图框架为中心的圆形。
- **Ellipse**：在包含它的视图框架内对齐的椭圆。
- **Capsule**：在包含它的视图框架内对齐的胶囊形状。

## 绘制自定义形状

- **Path**：二维形状的轮廓。

## 定义形状行为

- **ShapeView**：提供形状的视图，可用于绘图操作。
- **Shape**：绘制视图时可以使用的 2D 形状。
- **AnyShape**：经过类型化的形状值。
- **ShapeRole**：形状的造型方法。
- **StrokeStyle**：描画路径的笔画特征。
- **StrokeShapeView**：对形状进行描边的形状提供者。
- **StrokeBorderShapeView**：会描边的形状提供程序。
- **FillStyle**：用于光栅化矢量形状的样式。
- **FillShapeView**：填充形状的形状提供程序。

## 变换形状

- **ScaledShape**：应用了缩放变换的形状。
- **RotatedShape**：应用了旋转变换的形状。
- **OffsetShape**：应用了平移偏移变换的形状。
- **TransformedShape**：应用了仿射变换的形状。

## 设置容器形状

- **containerShape(_:)**：为该视图中的任何容器相对形状或同心矩形设置容器形状。
- **InsettableShape**：一种形状类型，能够嵌入自身以生成另一个形状。
- **ContainerRelativeShape**：由当前容器形状的嵌入版本替换的形状。如果没有定义容器形状，则会被矩形替换。

## 意见

- 视图的基本原理**：使用视图层次结构定义应用程序的视觉元素。
- 视图配置**：调整层次结构中视图的特性。
- 视图样式**：为不同类型的视图应用内置和自定义外观和行为。
- **Animations**：根据状态变化创建平滑的可视化更新。
- 文本输入和输出**：显示格式化文本并从用户获取文本输入。
- **Images**：为应用程序的用户界面添加图像和符号。
- **控件和指示器**：显示数值并获取用户选择。
- 菜单和命令**：提供空间效率高、上下文相关的命令和控件访问。
- 绘图和图形**：通过图形效果和自定义绘图来增强视图。


---
source: https://developer.apple.com/documentation/SwiftUI/Shapes
crawled: 2025-12-02T16:02:52Z
---

# Shapes

**API Collection**

Trace and fill built-in and custom shapes with a color, gradient, or other pattern.

## Overview

Draw shapes like circles and rectangles, as well as custom paths that define shapes of your own design. Apply styles that include environment-aware colors, rich gradients, and material effects to the foreground, background, and outline of your shapes.



If you need the efficiency or flexibility of immediate mode drawing — for example, to create particle effects — use a [Canvas](Canvas.zh-Hans.md) view instead.

## Creating rectangular shapes

- **Rectangle**: A rectangular shape aligned inside the frame of the view containing it.
- **RoundedRectangle**: A rectangular shape with rounded corners, aligned inside the frame of the view containing it.
- **RoundedCornerStyle**: Defines the shape of a rounded rectangle’s corners.
- **RoundedRectangularShape**: A protocol of [InsettableShape](InsettableShape.zh-Hans.md) that describes a rounded rectangular shape.
- **RoundedRectangularShapeCorners**: A type describing the corner styles of a [RoundedRectangularShape](RoundedRectangularShape.zh-Hans.md).
- **UnevenRoundedRectangle**: A rectangular shape with rounded corners with different values, aligned inside the frame of the view containing it.
- **RectangleCornerRadii**: Describes the corner radius values of a rounded rectangle with uneven corners.
- **RectangleCornerInsets**: The inset sizes for the corners of a rectangle.
- **ConcentricRectangle**: A shape that is replaced by a concentric version of the current container shape. If the container shape is a rectangle derived shape with four corners, this shape could choose to respect corners individually.

## Creating circular shapes

- **Circle**: A circle centered on the frame of the view containing it.
- **Ellipse**: An ellipse aligned inside the frame of the view containing it.
- **Capsule**: A capsule shape aligned inside the frame of the view containing it.

## Drawing custom shapes

- **Path**: The outline of a 2D shape.

## Defining shape behavior

- **ShapeView**: A view that provides a shape that you can use for drawing operations.
- **Shape**: A 2D shape that you can use when drawing a view.
- **AnyShape**: A type-erased shape value.
- **ShapeRole**: Ways of styling a shape.
- **StrokeStyle**: The characteristics of a stroke that traces a path.
- **StrokeShapeView**: A shape provider that strokes its shape.
- **StrokeBorderShapeView**: A shape provider that strokes the border of its shape.
- **FillStyle**: A style for rasterizing vector shapes.
- **FillShapeView**: A shape provider that fills its shape.

## Transforming a shape

- **ScaledShape**: A shape with a scale transform applied to it.
- **RotatedShape**: A shape with a rotation transform applied to it.
- **OffsetShape**: A shape with a translation offset transform applied to it.
- **TransformedShape**: A shape with an affine transform applied to it.

## Setting a container shape

- **containerShape(_:)**: Sets the container shape to use for any container relative shape or concentric rectangle within this view.
- **InsettableShape**: A shape type that is able to inset itself to produce another shape.
- **ContainerRelativeShape**: A shape that is replaced by an inset version of the current container shape. If no container shape was defined, is replaced by a rectangle.

## Views

- **View fundamentals**: Define the visual elements of your app using a hierarchy of views.
- **View configuration**: Adjust the characteristics of views in a hierarchy.
- **View styles**: Apply built-in and custom appearances and behaviors to different types of views.
- **Animations**: Create smooth visual updates in response to state changes.
- **Text input and output**: Display formatted text and get text input from the user.
- **Images**: Add images and symbols to your app’s user interface.
- **Controls and indicators**: Display values and get user selections.
- **Menus and commands**: Provide space-efficient, context-dependent access to commands and controls.
- **Drawing and graphics**: Enhance your views with graphical effects and customized drawings.

