---
来源： https://developer.apple.com/documentation/SwiftUI/PointerStyle/grabIdle
抓取时间： 2025-12-03T06:45:12Z
---

# grabIdle

**类型属性**

指针样式，用于表示可以在特定范围内拖动以重新定位内容，例如平移大图像。

### 声明

```swift
static let grabIdle: PointerStyle
```

## 讨论

这种指针样式显示一只张开的手，表示内容可以重新定位。通常情况下，当鼠标或触控板被主动点击时，它会与`PointerStyle.grabActive`指针样式一起使用，以指示当前正在重新定位的内容。

您可以使用[pointerStyle(_:)](../View/pointerStyle.zh-Hans.md)修饰符将此指针样式应用于单个视图或视图层次结构。

## 获取内置指针样式

- **default**：使用默认平台外观的指针样式。
- **horizontalText**：适合在水平布局中选择或插入文本的指针样式。
- **verticalText**：适合在垂直布局中选择或插入文本的指针样式。
- **rectSelection**：适合在垂直布局中选择或插入文本的指针样式：适用于精确矩形选择的指针样式，例如选择图像的一部分或多行文本。
- **grabActive**：适合在特定范围内主动拖动以重新定位内容的指针样式，如平移大图像。
- **link**：适合内容的指针样式，点击后会打开指向网页、文档或其他项目的 URL 链接。
- **zoomIn**：适合表示内容可以放大的指针样式。
- **zoomOut**：适合表示内容可以放大的指针样式。
- **frameResize(position:directions:)**：用于从特定边缘或角落调整矩形框架大小的指针样式。
- **columnResize(directions:)**：用于调整列或垂直分割大小的指针样式。
- **rowResize(directions:)**：用于调整行大小或水平分割的指针样式。


---
source: https://developer.apple.com/documentation/SwiftUI/PointerStyle/grabIdle
crawled: 2025-12-03T06:45:12Z
---

# grabIdle

**Type Property**

The pointer style appropriate to indicate that dragging to reposition content within specific bounds, such as panning a large image, is possible.

## Declaration

```swift
static let grabIdle: PointerStyle
```

## Discussion

This pointer style displays an open hand to indicate that the content can be repositioned. Typically it’s used along with the `PointerStyle.grabActive` pointer style while a mouse or trackpad is actively clicked to indicate that the content is currently being repositioned.

You may apply this pointer style to a single view or a view hierarchy using the [pointerStyle(_:)](../View/pointerStyle.zh-Hans.md) modifier.

## Getting built-in pointer styles

- **default**: The pointer style that uses the default platform appearance.
- **horizontalText**: The pointer style appropriate for selecting or inserting text in a horizontal layout.
- **verticalText**: The pointer style appropriate for selecting or inserting text in a vertical layout.
- **rectSelection**: The pointer style appropriate for precise rectangular selection, such as selecting a portion of an image or multiple lines of text.
- **grabActive**: The pointer style appropriate for actively dragging to reposition content within specific bounds, such as panning a large image.
- **link**: The pointer style appropriate for content opens a URL link to a webpage, document, or other item when clicked.
- **zoomIn**: The pointer style appropriate to indicate that the content can be zoomed in.
- **zoomOut**: The pointer style appropriate to indicate that the content can be zoomed out.
- **frameResize(position:directions:)**: The pointer style for resizing a rectangular frame from a specific edge or corner.
- **columnResize(directions:)**: The pointer style for resizing a column, or vertical division.
- **rowResize(directions:)**: The pointer style for resizing a row, or horizontal division.

