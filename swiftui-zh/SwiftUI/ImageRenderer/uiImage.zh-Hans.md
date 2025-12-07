---
来源： https://developer.apple.com/documentation/SwiftUI/ImageRenderer/uiImage
抓取时间： 2025-12-03T06:21:49Z
---

# uiImage

**实例属性**

视图的当前内容，光栅化为 UIKit 图像。

## 声明

```swift
@MainActor final var uiImage: UIImage? { get }
```

## 讨论

当图像内容发生变化时，呈现器会通知其 `objectWillChange` 发布者。

## 渲染图像

- **render(rasterizationScale:renderer:)**：将呈现器的当前内容绘制到任意 Core Graphics 上下文中。
- **cgImage**：视图的当前内容，光栅化为 Core Graphics 图像。
- **nsImage**：视图的当前内容，光栅化为 AppKit 图像。


---
source: https://developer.apple.com/documentation/SwiftUI/ImageRenderer/uiImage
crawled: 2025-12-03T06:21:49Z
---

# uiImage

**Instance Property**

The current contents of the view, rasterized as a UIKit image.

## Declaration

```swift
@MainActor final var uiImage: UIImage? { get }
```

## Discussion

The renderer notifies its `objectWillChange` publisher when the contents of the image may have changed.

## Rendering images

- **render(rasterizationScale:renderer:)**: Draws the renderer’s current contents to an arbitrary Core Graphics context.
- **cgImage**: The current contents of the view, rasterized as a Core Graphics image.
- **nsImage**: The current contents of the view, rasterized as an AppKit image.

