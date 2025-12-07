--- 来源：https://developer.apple.com/documentation/SwiftUI/Landmarks-Applying-a-background-extension-effect

抓取时间：2025-12-02T15:45:37Z

---

# 地标：应用背景扩展效果

**示例代码**

配置图像，使其在侧边栏或检查器面板下方模糊并扩展显示。

## 概述

“地标”应用让用户探索世界各地的有趣景点。无论是家附近的国家公园，还是遥远的异国他乡，该应用都能帮助用户记录和标记他们的探险之旅，并在此过程中获得自定义活动徽章。

此示例演示如何应用背景扩展效果。在顶部“地标”视图中，此示例将背景扩展效果应用于 `LandmarksView` 中的特色图像和 `LandmarkDetailView` 中的主图像。背景扩展效果会在侧边栏或检查器面板打开时模糊并扩展其下方的图像。以下图片展示了 `LandmarkDetailView` 中的主图像在启用和禁用背景扩展效果时的效果。

要应用背景扩展效果，请执行以下操作：

1. 将视图与包含视图的前缘和后缘对齐。

2. 将 [backgroundExtensionEffect()](View/backgroundExtensionEffect.zh-Hans.md) 修饰符应用于视图。

3. 仅配置背景扩展中的图像，避免将效果应用于叠加层中的标题和按钮。

### 将视图与前缘和后缘对齐

要将 [backgroundExtensionEffect()](View/backgroundExtensionEffect.zh-Hans.md) 应用于视图，请将视图的前缘与侧边栏对齐，并将视图的后缘与包含视图的后缘对齐。

在 `LandmarksView` 中，`LandmarkFeaturedItemView` 及其包含的 [LazyVStack](LazyVStack.zh-Hans.md) 和 [ScrollView](ScrollView.zh-Hans.md) 没有内边距。这使得 `LandmarkFeaturedItemView` 可以与侧边栏旁边的视图边缘对齐。

```swift
ScrollView(showsIndicators: false) {
    LazyVStack(alignment: .leading, spacing: Constants.standardPadding) {
        LandmarkFeaturedItemView(landmark: modelData.featuredLandmark!)
            .flexibleHeaderContent()
        //...
    }
}
```

在 `LandmarkDetailView` 中，包含主图像的 [ScrollView](ScrollView.zh-Hans.md) 和 [VStack](VStack.zh-Hans.md) 也没有任何内边距。这使得主图像可以与包含视图的边缘对齐。

### 将背景扩展效果应用于图像

在 `LandmarkDetailView` 中，示例通过添加 [backgroundExtensionEffect()](View/backgroundExtensionEffect.zh-Hans.md) 修改器将背景扩展效果应用于主图像：

```swift
Image(landmark.backgroundImageName)
    //...
    .backgroundExtensionEffect()
```

当侧边栏打开时，系统会按如下方式沿前缘方向扩展图像：

- 系统会截取图像前端与侧边栏宽度相同的部分。

- 系统会将图像的该部分沿水平方向翻转至前缘，并对翻转后的部分应用模糊效果。

- 系统会将修改后的图像部分放置在侧边栏下方，紧邻图像前缘。

当检查器打开时，系统会按如下方式沿后缘方向扩展图像：

- 系统会截取图像后缘与侧边栏宽度相同的部分。

- 系统会将图像的该部分水平翻转至后缘，并对翻转后的部分应用模糊效果。

- 系统会将修改后的图像部分放置在检查器下方，紧接图像的后缘。

### 仅配置图像

在 `LandmarksView` 中，`LandmarkFeaturedItemView` 包含一张特色地标的图像，以及地标的标题和一个按钮，点击或轻触即可了解更多关于该地点的信息。

为了避免地标的标题和按钮出现在 macOS 的侧边栏下方，示例在添加包含标题和按钮的叠加层之前，对图像应用了 [backgroundExtensionEffect()](View/backgroundExtensionEffect.zh-Hans.md) 修饰符：

```swift
Image(decorative: landmark.backgroundImageName)
    //...
    .backgroundExtensionEffect()
    .overlay(alignment: .bottom) {
        VStack {
            Text("Featured Landmark", comment: "Big headline in the main image of featured landmarks.")
                //...
            Text(landmark.name)
                //...
            Button("Learn More") {
                modelData.path.append(landmark)
            }
            //...
        }
        .padding([.bottom], Constants.learnMoreBottomPadding)
    }

```

## 应用功能

- **地标：在侧边栏或检查器下方扩展水平滚动条**：通过将水平滚动条扩展到侧边栏或检查器下方，改善其外观。

- **重要改进：优化工具栏的液态玻璃效果**：将工具栏按相关类别分组，以提升其外观和实用性。

- **重要改进：显示自定义活动徽章**：为用户提供展示动画自定义活动徽章的方式，让他们能够记录自己的精彩旅程。


---
source: https://developer.apple.com/documentation/SwiftUI/Landmarks-Applying-a-background-extension-effect
crawled: 2025-12-02T15:45:37Z
---

# Landmarks: Applying a background extension effect

**Sample Code**

Configure an image to blur and extend under a sidebar or inspector panel.

## Overview

The Landmarks app lets people explore interesting sites around the world. Whether it’s a national park near their home or a far-flung location on a different continent, the app provides a way for people to organize and mark their adventures and receive custom activity badges along the way.

This sample demonstrates how to apply a background extension effect. In the top Landmarks view, the sample applies a background extension effect to the featured image in `LandmarksView`, and to the main image in `LandmarkDetailView`. The background extension effect blurs and extends the image under the sidebar or inspector panel when open. The following images show the main image in `LandmarkDetailView` both with and without the background extension effect.



To apply the background extension effect, the sample:

1. Aligns the view to the leading and trailing edges of the containing view.
2. Applies the [backgroundExtensionEffect()](View/backgroundExtensionEffect.zh-Hans.md) modifier to the view.
3. Configures only the image in the background extension, and avoids applying the effect to the title and button in the overlay.

### Align the view to the leading and trailing edges

To apply the [backgroundExtensionEffect()](View/backgroundExtensionEffect.zh-Hans.md) to a view, align the leading edge of the view next to the sidebar, and align the trailing edge of the view to the trailing edge of the containing view.

In `LandmarksView`, the `LandmarkFeaturedItemView` and the containing [LazyVStack](LazyVStack.zh-Hans.md) and [ScrollView](ScrollView.zh-Hans.md) don’t have padding. This allows the `LandmarkFeaturedItemView` to align with the leading edge of the view next to the sidebar.

```swift
ScrollView(showsIndicators: false) {
    LazyVStack(alignment: .leading, spacing: Constants.standardPadding) {
        LandmarkFeaturedItemView(landmark: modelData.featuredLandmark!)
            .flexibleHeaderContent()
        //...
    }
}
```

In `LandmarkDetailView`, the [ScrollView](ScrollView.zh-Hans.md) and [VStack](VStack.zh-Hans.md) that contain the main image also don’t have any padding. This allows the main image to align against the leading edge of the containing view.

### Apply the background extension effect to the image

In `LandmarkDetailView`, the sample applies the background extension effect to the main image by adding the [backgroundExtensionEffect()](View/backgroundExtensionEffect.zh-Hans.md) modifier:

```swift
Image(landmark.backgroundImageName)
    //...
    .backgroundExtensionEffect()
```

When the sidebar is open, the system extends the image in the leading direction as follows:

- The system takes a section of the leading end of the image that matches the width of the sidebar.
- The system flips that portion of the image horizontally toward the leading edge and applies a blur to the flipped section.
- The system places the modified section of the image under the sidebar, immediately before the leading edge of the image.

When the inspector is open, the system extends the image in the trailing direction as follows:

- The system takes a section of the trailing end of the image that matches the width of the sidebar.
- The system flips that portion of the image horizontally toward the trailing edge and applies a blur to the flipped section.
- The system places the modified section of the image under the inspector, immediately after the trailing edge of the image.

### Configure only the image

In `LandmarksView`, the `LandmarkFeaturedItemView` has an image from the featured landmark, and includes a title for the landmark and a button you can click or tap to learn more about that location.

To avoid having the landmark’s title and button appear under the sidebar in macOS, the sample applies the [backgroundExtensionEffect()](View/backgroundExtensionEffect.zh-Hans.md) modifier to the image before adding the overlay that includes the title and button:

```swift
Image(decorative: landmark.backgroundImageName)
    //...
    .backgroundExtensionEffect()
    .overlay(alignment: .bottom) {
        VStack {
            Text("Featured Landmark", comment: "Big headline in the main image of featured landmarks.")
                //...
            Text(landmark.name)
                //...
            Button("Learn More") {
                modelData.path.append(landmark)
            }
            //...
        }
        .padding([.bottom], Constants.learnMoreBottomPadding)
    }

```

## App features

- **Landmarks: Extending horizontal scrolling under a sidebar or inspector**: Improve your horizontal scrollbar’s appearance by extending it under a sidebar or inspector.
- **Landmarks: Refining the system provided Liquid Glass effect in toolbars**: Organize toolbars into related groupings to improve their appearance and utility.
- **Landmarks: Displaying custom activity badges**: Provide people with a way to mark their adventures by displaying animated custom activity badges.

