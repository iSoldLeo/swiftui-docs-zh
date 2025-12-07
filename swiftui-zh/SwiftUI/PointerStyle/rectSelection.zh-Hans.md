---
来源： https://developer.apple.com/documentation/SwiftUI/PointerStyle/rectSelection
抓取时间： 2025-12-03T06:45:12Z
---

# rectSelection

**类型属性**

适合精确矩形选择的指针样式，例如选择图像的一部分或多行文本。

## 声明

```swift
static let rectSelection: PointerStyle
```

## 讨论

这种指针样式显示十字准线。您可以使用 [pointerStyle(_:)](../View/pointerStyle.zh-Hans.md) 修改器将此指针样式应用于单个视图或视图层次结构。

## 获取内置指针样式

- **default**：使用默认平台外观的指针样式。
- **horizontalText**：适合在水平布局中选择或插入文本的指针样式。
- **verticalText**：适合在水平布局中选择或插入文本的指针样式：适合在垂直布局中选择或插入文本的指针样式。
- **grabIdle**：指针样式适用于表示在特定范围内拖动以重新定位内容（如平移大图像）。
- **grabActive**：适合主动拖动以在特定范围内重新定位内容（如平移大图像）的指针样式。
- **link**：适合内容的指针样式，点击后会打开指向网页、文档或其他项目的 URL 链接。
- **zoomIn**：适合表示内容可以放大的指针样式。
- **zoomOut**：适合表示内容可以放大的指针样式。
- **frameResize(position:directions:)**：用于从特定边缘或角落调整矩形框架大小的指针样式。
- **columnResize(directions:)**：用于调整列或垂直分割大小的指针样式。
- **rowResize(directions:)**：用于调整行大小或水平分割的指针样式。


---
source: https://developer.apple.com/documentation/SwiftUI/PointerStyle/rectSelection
crawled: 2025-12-03T06:45:12Z
---

# rectSelection

**Type Property**

The pointer style appropriate for precise rectangular selection, such as selecting a portion of an image or multiple lines of text.

## Declaration

```swift
static let rectSelection: PointerStyle
```

## Discussion

This pointer style displays a crosshair. You may apply this pointer style to a single view or a view hierarchy using the [pointerStyle(_:)](../View/pointerStyle.zh-Hans.md) modifier.

## Getting built-in pointer styles

- **default**: The pointer style that uses the default platform appearance.
- **horizontalText**: The pointer style appropriate for selecting or inserting text in a horizontal layout.
- **verticalText**: The pointer style appropriate for selecting or inserting text in a vertical layout.
- **grabIdle**: The pointer style appropriate to indicate that dragging to reposition content within specific bounds, such as panning a large image, is possible.
- **grabActive**: The pointer style appropriate for actively dragging to reposition content within specific bounds, such as panning a large image.
- **link**: The pointer style appropriate for content opens a URL link to a webpage, document, or other item when clicked.
- **zoomIn**: The pointer style appropriate to indicate that the content can be zoomed in.
- **zoomOut**: The pointer style appropriate to indicate that the content can be zoomed out.
- **frameResize(position:directions:)**: The pointer style for resizing a rectangular frame from a specific edge or corner.
- **columnResize(directions:)**: The pointer style for resizing a column, or vertical division.
- **rowResize(directions:)**: The pointer style for resizing a row, or horizontal division.

