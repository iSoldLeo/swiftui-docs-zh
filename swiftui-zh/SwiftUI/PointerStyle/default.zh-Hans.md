---
来源： https://developer.apple.com/documentation/SwiftUI/PointerStyle/default
抓取时间： 2025-12-03T06:45:09Z
---

# 默认

**类型属性**

使用默认平台外观的指针样式。

## 声明

```swift
static let `default`: PointerStyle
```

## 讨论

如果没有其他更合适的指针样式，这是用于与内容和 UI 元素交互的默认指针样式。这种指针样式在 macOS 中显示箭头，在 iPadOS 和 visionOS 中显示圆形。

您可能需要使用[pointerStyle(_:)](../View/pointerStyle.zh-Hans.md)修改器显式设置该指针样式，以覆盖环境中的其他样式。

## 获取内置指针样式

- **horizontalText**：适合在水平布局中选择或插入文本的指针样式。
- **verticalText**：适合在垂直布局中选择或插入文本的指针样式。
- **rectSelection**：适合在垂直布局中选择或插入文本的指针样式：适用于精确矩形选择的指针样式，例如选择图像的一部分或多行文本。
- **grabIdle**：指针样式适用于在特定范围内拖动以重新定位内容，如平移大图像。
- **grabActive**：适合主动拖动以在特定范围内重新定位内容（如平移大图像）的指针样式。
- **link**：适合内容的指针样式，点击后会打开指向网页、文档或其他项目的 URL 链接。
- **zoomIn**：适合表示内容可以放大的指针样式。
- **zoomOut**：适合表示内容可以放大的指针样式。
- **frameResize(position:directions:)**：用于从特定边缘或角落调整矩形框架大小的指针样式。
- **columnResize(directions:)**：用于调整列或垂直分割大小的指针样式。
- **rowResize(directions:)**：用于调整行大小或水平分割的指针样式。


---
source: https://developer.apple.com/documentation/SwiftUI/PointerStyle/default
crawled: 2025-12-03T06:45:09Z
---

# default

**Type Property**

The pointer style that uses the default platform appearance.

## Declaration

```swift
static let `default`: PointerStyle
```

## Discussion

This is the default pointer style for interacting with content and UI elements if no other pointer style is more appropriate. This pointer style displays an arrow in macOS and a circle in iPadOS and visionOS.

You might want to set this pointer style explicitly using the [pointerStyle(_:)](../View/pointerStyle.zh-Hans.md) modifier to override another style in the environment.

## Getting built-in pointer styles

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

