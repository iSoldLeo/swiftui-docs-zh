---
来源：https://developer.apple.com/documentation/SwiftUI/PointerStyle/frameResize(位置:方向:)
抓取时间：2025-12-03T06:45:16Z
---

# frameResize(position:directions:)

**类型方法**

指针样式，用于从特定边缘或角落调整矩形框架的大小。

## 声明

```swift
static func frameResize(position: FrameResizePosition, directions: FrameResizeDirection.Set = .all) -> PointerStyle
```

## 参数

- **position**：调整边框大小时沿边框周长（边和角）的位置。
- **directions**：调整边框大小的方向。

## 获取内置指针样式

- **default**：使用默认平台外观的指针样式。
- **horizontalText**：适合在水平布局中选择或插入文本的指针样式。
- **verticalText**：适合在水平布局中选择或插入文本的指针样式：适合在垂直布局中选择或插入文本的指针样式。
- **rectSelection**：适合在垂直布局中选择或插入文本的指针样式：适用于精确矩形选择的指针样式，例如选择图像的一部分或多行文本。
- **grabIdle**：指针样式适用于表示在特定范围内拖动以重新定位内容（如平移大图像）。
- **grabActive**：适合主动拖动以在特定范围内重新定位内容（如平移大图像）的指针样式。
- **link**：适合内容的指针样式，点击后会打开指向网页、文档或其他项目的 URL 链接。
- **zoomIn**：适合表示内容可以放大的指针样式。
- **zoomOut**：适合表示内容可以放大的指针样式。
- **columnResize(directions:)**：用于调整列或垂直分区大小的指针样式。
- **rowResize(directions:)**：用于调整行大小或水平分割的指针样式。


---
source: https://developer.apple.com/documentation/SwiftUI/PointerStyle/frameResize(position:directions:)
crawled: 2025-12-03T06:45:16Z
---

# frameResize(position:directions:)

**Type Method**

The pointer style for resizing a rectangular frame from a specific edge or corner.

## Declaration

```swift
static func frameResize(position: FrameResizePosition, directions: FrameResizeDirection.Set = .all) -> PointerStyle
```

## Parameters

- **position**: The position along the perimeter of the frame (its edges and corners) from which it’s resized.
- **directions**: The directions in which the frame can be resized.

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
- **columnResize(directions:)**: The pointer style for resizing a column, or vertical division.
- **rowResize(directions:)**: The pointer style for resizing a row, or horizontal division.

