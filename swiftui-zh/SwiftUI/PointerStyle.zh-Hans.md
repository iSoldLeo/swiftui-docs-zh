--- 来源：https://developer.apple.com/documentation/SwiftUI/PointerStyle
抓取时间：2025-12-02T17:41:56Z

---

# PointerStyle

**Structure**

一种描述鼠标悬停在视图上时指针（也称为光标）外观的样式。

## 声明

```swift
struct PointerStyle
```

## 概述

使用 [pointerStyle(_:)](View/pointerStyle.zh-Hans.md) 视图修饰符来设置视图的指针样式。

有关如何选择合适的指针样式的指导，请参阅人机界面指南中的 [doc://com.apple.documentation/design/Human-Interface-Guidelines/pointing-devices]。

## 获取内置指针样式

- **default**：使用平台默认外观的指针样式。

- **horizontalText**：适用于水平布局中选择或插入文本的指针样式。

- **verticalText**：适用于垂直布局中选择或插入文本的指针样式。

- **rectSelection**：适用于精确矩形选择的指针样式，例如选择图像的一部分或多行文本。

- **grabIdle**：适用于指示可以在特定范围内拖动以重新定位内容的指针样式，例如平移大图像。

- **grabActive**：适用于主动拖动以重新定位特定范围内的内容的指针样式，例如平移大图像。

- **link**：适用于单击内容时打开指向网页、文档或其他项目的 URL 链接的指针样式。

- **zoomIn**：用于指示内容可以放大的指针样式。

- **zoomOut**：用于指示内容可以缩小的指针样式。

- **frameResize(position:directions:)**：用于从特定边或角调整矩形框大小的指针样式。

- **columnResize(directions:)**：用于调整列（或垂直分隔线）大小的指针样式。

- **rowResize(directions:)**：用于调整行（或水平分隔线）大小的指针样式。

## 创建自定义指针样式

- **image(_:hotSpot:)**：使用给定的图像和热点初始化指针样式。

- **shape(_:eoFill:size:)**：使用给定的形状初始化指针样式。

## 支持类型

- **HorizontalDirection**：水平轴方向。

- **VerticalDirection**：水平轴方向。

- **FrameResizePosition**：矩形框（包括其边缘和角）的调整位置。

- **FrameResizeDirection**：矩形框的调整方向。

## 类型属性

- **columnResize**：用于调整列（或垂直分隔线）大小的指针样式（可沿任一方向调整）。

- **rowResize**：用于调整行（或水平分隔线）大小的指针样式（可沿任一方向调整）。

## 修改指针外观

- **pointerStyle(_:)**：设置指针悬停在视图上时显示的指针样式。

- **pointerVisibility(_:)**：设置指针悬停在视图上时的可见性。

## 符合以下标准

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/PointerStyle
crawled: 2025-12-02T17:41:56Z
---

# PointerStyle

**Structure**

A style describing the appearance of the pointer (also called a cursor) when it’s hovered over a view.

## Declaration

```swift
struct PointerStyle
```

## Overview

Use the [pointerStyle(_:)](View/pointerStyle.zh-Hans.md) view modifier to set a view’s pointer style.

For guidance on choosing an appropriate pointer style, refer to [doc://com.apple.documentation/design/Human-Interface-Guidelines/pointing-devices] in the Human Interface Guidelines.

## Getting built-in pointer styles

- **default**: The pointer style that uses the default platform appearance.
- **horizontalText**: The pointer style appropriate for selecting or inserting text in a horizontal layout.
- **verticalText**: The pointer style appropriate for selecting or inserting text in a vertical layout.
- **rectSelection**: The pointer style appropriate for precise rectangular selection, such as selecting a portion of an image or multiple lines of text.
- **grabIdle**: The pointer style appropriate to indicate that dragging to reposition content within specific bounds, such as panning a large image, is possible.
- **grabActive**: The pointer style appropriate for actively dragging to reposition content within specific bounds, such as panning a large image.
- **link**: The pointer style appropriate for content opens a URL link to a webpage, document, or other item when clicked.
- **zoomIn**: The pointer style appropriate to indicate that the content can be zoomed in.
- **zoomOut**: The pointer style appropriate to indicate that the content can be zoomed out.
- **frameResize(position:directions:)**: The pointer style for resizing a rectangular frame from a specific edge or corner.
- **columnResize(directions:)**: The pointer style for resizing a column, or vertical division.
- **rowResize(directions:)**: The pointer style for resizing a row, or horizontal division.

## Creating custom pointer styles

- **image(_:hotSpot:)**: Initializes a pointer style with a given image and hot spot.
- **shape(_:eoFill:size:)**: Initializes a pointer style with a given shape.

## Supporting types

- **HorizontalDirection**: A direction on the horizontal axis.
- **VerticalDirection**: A direction on the horizontal axis.
- **FrameResizePosition**: The position along the perimeter of a rectangular frame (its edges and corners) from which it’s resized.
- **FrameResizeDirection**: The direction in which a rectangular frame can be resized.

## Type Properties

- **columnResize**: The pointer style for resizing a column, or vertical division, in either direction.
- **rowResize**: The pointer style for resizing a row, or horizontal division, in either direction.

## Modifying pointer appearance

- **pointerStyle(_:)**: Sets the pointer style to display when the pointer is over the view.
- **pointerVisibility(_:)**: Sets the visibility of the pointer when it’s over the view.

## Conforms To

- Sendable
- SendableMetatype

