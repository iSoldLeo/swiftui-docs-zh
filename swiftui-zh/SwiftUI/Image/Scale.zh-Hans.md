---
来源： https://developer.apple.com/documentation/SwiftUI/Image/Scale
抓取时间： 2025-12-02T17:35:48Z
---

# Image.Scale

**Enumeration**

相对于文本应用于矢量图像的缩放比例。

## 声明

```swift
enum Scale
```

## 概览

将此类型与[imageScale(_:)](../View/imageScale.zh-Hans.md) 修改器或[imageScale](../EnvironmentValues/imageScale.zh-Hans.md) 环境键一起使用，可设置图像比例。

下面的示例显示了应用于系统符号图像的三个`Scale` 值，每个值都与文本视图相对应：

```swift
HStack { Image(systemName: "swift").imageScale(.small); Text("Small") }
HStack { Image(systemName: "swift").imageScale(.medium); Text("Medium") }
HStack { Image(systemName: "swift").imageScale(.large); Text("Large") }
```



## 获取图像比例

- **Image.Scale.small**：生成小图像的缩放比例。
- **Image.Scale.medium**：生成中等大小图像的比例尺。
- **Image.Scale.large**：产生大图像的比例尺。

## 配置图像

- 将图像调整到可用空间**：通过应用视图修改器来调整应用程序用户界面中图像的大小和形状。
- **imageScale(_:)**：根据可用的相对尺寸（包括小尺寸、中尺寸和大尺寸）之一缩放视图中的图像。
- **imageScale**：此环境的图像比例。
- **Image.Orientation**：图像的方向。
- **Image.ResizingMode**：SwiftUI 用来调整图像大小以适合其包含的视图的模式。

## 符合

- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/Image/Scale
crawled: 2025-12-02T17:35:48Z
---

# Image.Scale

**Enumeration**

A scale to apply to vector images relative to text.

## Declaration

```swift
enum Scale
```

## Overview

Use this type with the [imageScale(_:)](../View/imageScale.zh-Hans.md) modifier, or the [imageScale](../EnvironmentValues/imageScale.zh-Hans.md) environment key, to set the image scale.

The following example shows the three `Scale` values as applied to a system symbol image, each set against a text view:

```swift
HStack { Image(systemName: "swift").imageScale(.small); Text("Small") }
HStack { Image(systemName: "swift").imageScale(.medium); Text("Medium") }
HStack { Image(systemName: "swift").imageScale(.large); Text("Large") }
```



## Getting image scales

- **Image.Scale.small**: A scale that produces small images.
- **Image.Scale.medium**: A scale that produces medium-sized images.
- **Image.Scale.large**: A scale that produces large images.

## Configuring an image

- **Fitting images into available space**: Adjust the size and shape of images in your app’s user interface by applying view modifiers.
- **imageScale(_:)**: Scales images within the view according to one of the relative sizes available including small, medium, and large images sizes.
- **imageScale**: The image scale for this environment.
- **Image.Orientation**: The orientation of an image.
- **Image.ResizingMode**: The modes that SwiftUI uses to resize an image to fit within its containing view.

## Conforms To

- Equatable
- Hashable
- Sendable
- SendableMetatype

