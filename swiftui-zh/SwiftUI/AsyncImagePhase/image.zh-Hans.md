---
来源： https://developer.apple.com/documentation/SwiftUI/AsyncImagePhase/image
抓取时间： 2025-12-03T06:21:18Z
---

# 图像

**实例属性**

已加载的图像（如果有）。

## 声明

```swift
var image: Image? { get }
```

## 讨论

如果该值不是 `nil`，则图像加载操作已经完成，您可以使用图像更新视图。您可以直接使用图像，也可以以某种方式修改图像。例如，您可以添加[resizable(capInsets:resizingMode:)](../Image/resizable_capInsets_resizingMode.zh-Hans.md) 修改器来调整图像大小。


---
source: https://developer.apple.com/documentation/SwiftUI/AsyncImagePhase/image
crawled: 2025-12-03T06:21:18Z
---

# image

**Instance Property**

The loaded image, if any.

## Declaration

```swift
var image: Image? { get }
```

## Discussion

If this value isn’t `nil`, the image load operation has finished, and you can use the image to update the view. You can use the image directly, or you can modify it in some way. For example, you can add a [resizable(capInsets:resizingMode:)](../Image/resizable_capInsets_resizingMode.zh-Hans.md) modifier to make the image resizable.

