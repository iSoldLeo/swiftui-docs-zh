---
来源： https://developer.apple.com/documentation/SwiftUI/ImageRenderer/render(rasterizationScale:renderer:)
抓取时间：2025-12-03T06:21:46Z
---

# render(rasterizationScale:renderer:)

**实例方法**

将呈现器的当前内容绘制到任意 Core Graphics 上下文中。

## 声明

```swift
@MainActor final func render(rasterizationScale: CGFloat = 1, renderer: (CGSize, (CGContext) -> Void) -> Void)
```

## 参数

- **rasterizationScale**：当光栅化视图中无法用本地 Core Graphics 绘图命令表示的部分时，将用户界面点转换为像素的比例因子。
- **renderer**：用于设置 Core Graphics 上下文并渲染视图的闭包。该闭包接收两个参数：视图大小和在闭包中调用的函数，以报告的大小渲染视图。该函数接收一个[doc://com.apple.documentation/documentation/CoreGraphics/CGContext]参数，并假定左下角为坐标空间原点。

### 讨论

使用此方法可将呈现器的内容光栅化为您提供的[doc://com.apple.documentation/documentation/CoreGraphics/CGContext]。`renderer`闭包接收两个参数：视图的当前大小，以及一个将视图渲染为您提供的`CGContext`的函数。实现闭包以提供合适的 `CGContext`，然后调用函数将内容呈现到该上下文中。

## 渲染图像

- **cgImage**：视图的当前内容，光栅化为 Core Graphics 图像。
- **nsImage**：视图的当前内容，光栅化为 AppKit 图像。
- **uiImage**：视图的当前内容，光栅化为 UIKit 图像。


---
source: https://developer.apple.com/documentation/SwiftUI/ImageRenderer/render(rasterizationScale:renderer:)
crawled: 2025-12-03T06:21:46Z
---

# render(rasterizationScale:renderer:)

**Instance Method**

Draws the renderer’s current contents to an arbitrary Core Graphics context.

## Declaration

```swift
@MainActor final func render(rasterizationScale: CGFloat = 1, renderer: (CGSize, (CGContext) -> Void) -> Void)
```

## Parameters

- **rasterizationScale**: The scale factor for converting user interface points to pixels when rasterizing parts of the view that can’t be represented as native Core Graphics drawing commands.
- **renderer**: The closure that sets up the Core Graphics context and renders the view. This closure receives two parameters: the size of the view and a function that you invoke in the closure to render the view at the reported size. This function takes a [doc://com.apple.documentation/documentation/CoreGraphics/CGContext] parameter, and assumes a bottom-left coordinate space origin.

## Discussion

Use this method to rasterize the renderer’s content to a [doc://com.apple.documentation/documentation/CoreGraphics/CGContext] you provide. The `renderer` closure receives two parameters: the current size of the view, and a function that renders the view to your `CGContext`. Implement the closure to provide a suitable `CGContext`, then invoke the function to render the content to that context.

## Rendering images

- **cgImage**: The current contents of the view, rasterized as a Core Graphics image.
- **nsImage**: The current contents of the view, rasterized as an AppKit image.
- **uiImage**: The current contents of the view, rasterized as a UIKit image.

