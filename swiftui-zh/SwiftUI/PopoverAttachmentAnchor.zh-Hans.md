--- 来源：https://developer.apple.com/documentation/SwiftUI/PopoverAttachmentAnchor
抓取时间：2025-12-02T17:30:08Z

---

# PopoverAttachmentAnchor

**Enumeration**

弹出框的附件锚点。

## 声明

```swift
enum PopoverAttachmentAnchor
```

## 获取附件锚点

- **PopoverAttachmentAnchor.point(_:)**：弹出框的锚点，以单位点表示，描述相对于 SwiftUI 视图的可能对齐方式。

- **PopoverAttachmentAnchor.rect(_:)**：弹出框相对于源框架的锚点。

## 显示工作表、封面或弹出框

- **sheet(isPresented:onDismiss:content:)**：当您提供的布尔值绑定为真时，显示工作表。

- **sheet(item:onDismiss:content:)**：显示一个工作表，并将指定项作为工作表内容的数据源。

- **fullScreenCover(isPresented:onDismiss:content:)**：当绑定到您提供的布尔值且该值为真时，显示一个尽可能覆盖屏幕的模态视图。

- **fullScreenCover(item:onDismiss:content:)**：显示一个尽可能覆盖屏幕的模态视图，并将您提供的绑定作为工作表内容的数据源。

- **popover(item:attachmentAnchor:arrowEdge:content:)**：显示一个弹出框，并将指定项作为弹出框内容的数据源。

- **popover(isPresented:attachmentAnchor:arrowEdge:content:)**：当给定条件为真时，显示一个弹出框。


---
source: https://developer.apple.com/documentation/SwiftUI/PopoverAttachmentAnchor
crawled: 2025-12-02T17:30:08Z
---

# PopoverAttachmentAnchor

**Enumeration**

An attachment anchor for a popover.

## Declaration

```swift
enum PopoverAttachmentAnchor
```

## Getting attachment anchors

- **PopoverAttachmentAnchor.point(_:)**: The anchor point for the popover expressed as a unit point  that describes possible alignments relative to a SwiftUI view.
- **PopoverAttachmentAnchor.rect(_:)**: The anchor point for the popover relative to the source’s frame.

## Showing a sheet, cover, or popover

- **sheet(isPresented:onDismiss:content:)**: Presents a sheet when a binding to a Boolean value that you provide is true.
- **sheet(item:onDismiss:content:)**: Presents a sheet using the given item as a data source for the sheet’s content.
- **fullScreenCover(isPresented:onDismiss:content:)**: Presents a modal view that covers as much of the screen as possible when binding to a Boolean value you provide is true.
- **fullScreenCover(item:onDismiss:content:)**: Presents a modal view that covers as much of the screen as possible using the binding you provide as a data source for the sheet’s content.
- **popover(item:attachmentAnchor:arrowEdge:content:)**: Presents a popover using the given item as a data source for the popover’s content.
- **popover(isPresented:attachmentAnchor:arrowEdge:content:)**: Presents a popover when a given condition is true.

