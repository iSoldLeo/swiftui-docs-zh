--- 来源：https://developer.apple.com/documentation/SwiftUI/View/imageScale(_:)

抓取时间：2025-11-30T21:20:51Z

---

# imageScale(_:)

**实例方法**

根据可用的相对尺寸（包括小、中、大尺寸）缩放视图中的图像。

## 声明

```swift
nonisolated func imageScale(_ scale: Image.Scale) -> some View

```

## 参数

- **scale**：图像缩放枚举提供的相对尺寸之一。

## 说明

以下示例展示了相对缩放效果。系统会根据可用空间和要缩放的图像的配置选项，以相对尺寸渲染图像。

```swift
VStack {
    HStack {
        Image(systemName: "heart.fill")
            .imageScale(.small)
        Text("Small")
    }
    HStack {
        Image(systemName: "heart.fill")
            .imageScale(.medium)
        Text("Medium")
    }

    HStack {
        Image(systemName: "heart.fill")
            .imageScale(.large)
        Text("Large")
    }
}
```

## 配置图像

- **调整图像大小以适应可用空间**：通过应用视图修饰符来调整应用用户界面中图像的大小和形状。

- **imageScale**：此环境中的图像缩放比例。

- **Image.Scale**：应用于矢量图像相对于文本的缩放比例。

- **Image.Orientation**：图像的方向。

- **Image.ResizingMode**：SwiftUI 用于调整图像大小以适应其包含视图的模式。


---
source: https://developer.apple.com/documentation/SwiftUI/View/imageScale(_:)
crawled: 2025-11-30T21:20:51Z
---

# imageScale(_:)

**Instance Method**

Scales images within the view according to one of the relative sizes available including small, medium, and large images sizes.

## Declaration

```swift
nonisolated func imageScale(_ scale: Image.Scale) -> some View

```

## Parameters

- **scale**: One of the relative sizes provided by the image scale enumeration.

## Discussion

The example below shows the relative scaling effect. The system renders the image at a relative size based on the available space and configuration options of the image it is scaling.

```swift
VStack {
    HStack {
        Image(systemName: "heart.fill")
            .imageScale(.small)
        Text("Small")
    }
    HStack {
        Image(systemName: "heart.fill")
            .imageScale(.medium)
        Text("Medium")
    }

    HStack {
        Image(systemName: "heart.fill")
            .imageScale(.large)
        Text("Large")
    }
}
```



## Configuring an image

- **Fitting images into available space**: Adjust the size and shape of images in your app’s user interface by applying view modifiers.
- **imageScale**: The image scale for this environment.
- **Image.Scale**: A scale to apply to vector images relative to text.
- **Image.Orientation**: The orientation of an image.
- **Image.ResizingMode**: The modes that SwiftUI uses to resize an image to fit within its containing view.

