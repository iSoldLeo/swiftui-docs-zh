---
来源： https://developer.apple.com/documentation/SwiftUI/ImageRenderer/cgImage
抓取时间： 2025-12-03T06:21:47Z
---

# cgImage

**实例属性**

视图的当前内容，光栅化为核心图形图像。

## 声明

```swift
@MainActor final var cgImage: CGImage? { get }
```

## 讨论

当图像内容发生变化时，呈现器会通知其 `objectWillChange` 发布者。

## 渲染图像

- **render(rasterizationScale:renderer:)**：将呈现器的当前内容绘制到任意 Core Graphics 上下文中。
- **nsImage**：视图的当前内容，光栅化为 AppKit 图像。
- **uiImage**：视图的当前内容，光栅化为 UIKit 图像。


---
source: https://developer.apple.com/documentation/SwiftUI/ImageRenderer/cgImage
crawled: 2025-12-03T06:21:47Z
---

# cgImage

**Instance Property**

The current contents of the view, rasterized as a Core Graphics image.

## Declaration

```swift
@MainActor final var cgImage: CGImage? { get }
```

## Discussion

The renderer notifies its `objectWillChange` publisher when the contents of the image may have changed.

## Rendering images

- **render(rasterizationScale:renderer:)**: Draws the renderer’s current contents to an arbitrary Core Graphics context.
- **nsImage**: The current contents of the view, rasterized as an AppKit image.
- **uiImage**: The current contents of the view, rasterized as a UIKit image.

