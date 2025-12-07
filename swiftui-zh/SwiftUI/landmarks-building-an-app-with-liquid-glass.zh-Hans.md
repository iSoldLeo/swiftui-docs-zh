--- 来源：https://developer.apple.com/documentation/swiftui/landmarks-building-an-app-with-liquid-glass

抓取时间：2025-12-02T16:01:03Z

---

# Landmarks：使用 Liquid Glass 构建应用

**示例代码**

使用系统提供的和自定义的 Liquid Glass 增强您的应用体验。

## 概述

Landmarks 是一款 SwiftUI 应用，演示了如何使用全新动态且富有表现力的设计功能 Liquid Glass。Landmarks 应用让用户探索世界各地的有趣景点。无论是家附近的国家公园，还是遥远的异国他乡，这款应用都能帮助用户记录和标记他们的旅程，并在此过程中获得自定义活动徽章。Landmarks 可在 iPad、iPhone 和 Mac 上运行。

Landmarks 使用 [NavigationSplitView](NavigationSplitView.zh-Hans.md) 来组织和导航应用中的内容，并演示了几个优化 Liquid Glass 使用的关键概念：

- 使用背景扩展效果拉伸侧边栏和检查器后面的内容。

- 扩展侧边栏或检查器下方的水平滚动视图。

- 利用工具栏中系统提供的玻璃效果。

- 将 Liquid Glass 效果应用于自定义界面元素和动画。

- 使用图标编辑器 (Icon Composer) 构建新的应用图标。

该示例还演示了更改窗口大小和添加全局搜索的几种技巧。

## 应用背景扩展效果

该示例将背景扩展效果应用于顶部视图中的特色地标标题和地标详情视图中的主图像。此效果会在侧边栏和检查器打开时扩展并模糊其下方的图像，从而创建完整的边缘到边缘体验。

为了实现此效果，示例创建并配置了一个 [Image](Image.zh-Hans.md)，该组件延伸至包含视图的前缘和后缘，并将 [backgroundExtensionEffect()](View/backgroundExtensionEffect.zh-Hans.md) 修饰符应用于图像。对于特色图像，示例在修饰符后添加了一个带有标题和按钮的叠加层，以便只有图像延伸到侧边栏和检查器下方。

更多信息，请参阅 [Landmarks-Applying-a-background-extension-effect](Landmarks-Applying-a-background-extension-effect.zh-Hans.md)。

## 将水平滚动条延伸到侧边栏下方

在 `LandmarksView` 的每个洲板块中，`LandmarkHorizontalListView` 的实例会显示一个水平滚动的地标视图列表。打开后，地标视图可以滚动到侧边栏或检查器下方。

为了实现此效果，应用程序将滚动视图与包含视图的前缘和后缘对齐。

更多信息，请参阅 [Landmarks-Extending-horizontal-scrolling-under-a-sidebar-or-inspector](Landmarks-Extending-horizontal-scrolling-under-a-sidebar-or-inspector.zh-Hans.md)。

## 优化工具栏中的 Liquid Glass 效果

在 `LandmarkDetailView` 中，示例添加了以下工具栏项目：

- 分享地标

- 在“收藏夹”列表中添加或移除地标

- 在“收藏集”中添加或移除地标

- 显示或隐藏检查器

系统会自动将 Liquid Glass 应用于工具栏项目：

示例还将工具栏组织成相关组，而不是将所有按钮放在一个组中。更多信息，请参阅 [Landmarks-Refining-the-system-provided-glass-effect-in-toolbars](Landmarks-Refining-the-system-provided-glass-effect-in-toolbars.zh-Hans.md)。

## 使用 Liquid Glass 显示徽章

徽章为用户提供他们在 Landmarks 应用中记录的活动的视觉指示。当用户完成某个地标的全部四项活动后，即可获得该地标的徽章。示例使用自定义 Liquid Glass 元素和徽章，并演示如何将动画与 Liquid Glass 协调起来。

为了创建自定义 Liquid Glass 徽章，Landmarks 使用一个带有 `Image` 的视图来显示徽章的系统符号图像。徽章的背景六边形 `Image` 填充了自定义颜色。徽章视图使用 [glassEffect(_:in:)](View/glassEffect___in.zh-Hans.md) 修饰符将 Liquid Glass 应用于徽章。

为了演示系统通过 Liquid Glass 动画提供的变形效果，示例将徽章和切换按钮组织到一个 [GlassEffectContainer](GlassEffectContainer.zh-Hans.md) 中，并为每个徽章分配一个唯一的 [glassEffectID(_:in:)](View/glassEffectID___in.zh-Hans.md)。

更多信息，请参阅 [Landmarks-Displaying-custom-activity-badges](Landmarks-Displaying-custom-activity-badges.zh-Hans.md)。有关使用 Liquid Glass 构建自定义视图的信息，请参阅 [Applying-Liquid-Glass-to-custom-views](Applying-Liquid-Glass-to-custom-views.zh-Hans.md)。

## 使用 Icon Composer 创建应用图标

Landmarks 包含一个使用 Icon Composer 创建的动态且富有表现力的应用图标。您可以使用四层图层创建应用图标，系统会利用这些图层在用户移动设备时生成镜面高光，使图标呈现出如同光线反射在玻璃上的效果。用户还可以通过“设置”应用选择应用图标的浅色、深色、透明或着色版本，从而个性化图标。

有关创建新应用图标的更多信息，请参阅 [doc://com.apple.documentation/documentation/Xcode/creating-your-app-icon-using-icon-composer]。

有关设计指南，请参阅“人机界面指南”> [doc://com.apple.documentation/design/Human-Interface-Guidelines/app-icons]。

## 应用功能

- **地标：应用背景扩展效果**：配置图像以使其在侧边栏或检查器面板下方模糊和扩展。

- **地标：在侧边栏或检查器面板下方扩展水平滚动条**：通过在侧边栏或检查器面板下方扩展水平滚动条，改善其外观。

- **里程碑：优化工具栏中的 Liquid Glass 效果**：将工具栏按相关类别分组，以提升其外观和实用性。

- **里程碑：显示自定义活动徽章**：为用户提供通过显示动画自定义活动徽章来标记他们的经历的方式。

## 基本功能

- **采用 Liquid Glass**：了解如何将这种新材质应用到您的应用中。

- **学习 SwiftUI**：通过这套概念文章和示例代码，探索构建跨平台应用的技巧和方法。

- **探索 SwiftUI 示例应用**：使用 iPad 上的 Swift Playground 或 Xcode 探索这些 SwiftUI 示例，学习如何定义用户界面、响应用户交互以及管理数据流。

- **SwiftUI 更新**：了解 SwiftUI 的重要变更。


---
source: https://developer.apple.com/documentation/swiftui/landmarks-building-an-app-with-liquid-glass
crawled: 2025-12-02T16:01:03Z
---

# Landmarks: Building an app with Liquid Glass

**Sample Code**

Enhance your app experience with system-provided and custom Liquid Glass.

## Overview

Landmarks is a SwifUI app that demonstrates how to use the new dynamic and expressive design feature, Liquid Glass. The Landmarks app lets people explore interesting sites around the world. Whether it’s a national park near their home or a far-flung location on a different continent, the app provides a way for people to organize and mark their adventures and receive custom activity badges along the way. Landmarks runs on iPad, iPhone, and Mac.



Landmarks uses a [NavigationSplitView](NavigationSplitView.zh-Hans.md) to organize and navigate to content in the app, and demonstrates several key concepts to optimize the use of Liquid Glass:

- Stretching content behind the sidebar and inspector with the background extension effect.
- Extending horizontal scroll views under a sidebar or inspector.
- Leveraging the system-provided glass effect in toolbars.
- Applying Liquid Glass effects to custom interface elements and animations.
- Building a new app icon with Icon Composer.

The sample also demonstrates several techniques to use when changing window sizes, and for adding global search.

## Apply a background extension effect

The sample applies a background extension effect to the featured landmark header in the top view, and the main image in the landmark detail view. This effect extends and blurs the image under the sidebar and inspector when they’re open, creating a full edge-to-edge experience.



To achieve this effect, the sample creates and configures an [Image](Image.zh-Hans.md) that extends to both the leading and trailing edges of the containing view, and applies the [backgroundExtensionEffect()](View/backgroundExtensionEffect.zh-Hans.md) modifier to the image. For the featured image, the sample adds an overlay with a headline and button after the modifier, so that only the image extends under the sidebar and inspector.



For more information, see [Landmarks-Applying-a-background-extension-effect](Landmarks-Applying-a-background-extension-effect.zh-Hans.md).

## Extend horizontal scrolling under the sidebar

Within each continent section in `LandmarksView`, an instance of `LandmarkHorizontalListView` shows a horizontally scrolling list of landmark views. When open, the landmark views can scroll underneath the sidebar or inspector.

To achieve this effect, the app aligns the scroll views next to the leading and trailing edges of the containing view.



For more information, see [Landmarks-Extending-horizontal-scrolling-under-a-sidebar-or-inspector](Landmarks-Extending-horizontal-scrolling-under-a-sidebar-or-inspector.zh-Hans.md).

## Refine the Liquid Glass in the toolbar

In `LandmarkDetailView`, the sample adds toolbar items for:

- sharing a landmark
- adding or removing a landmark from a list of Favorites
- adding or removing a landmark from Collections
- showing or hiding the inspector

The system applies Liquid Glass to toolbar items automatically:



The sample also organizes the toolbar into related groups, instead of having all the buttons in one group. For more information, see [Landmarks-Refining-the-system-provided-glass-effect-in-toolbars](Landmarks-Refining-the-system-provided-glass-effect-in-toolbars.zh-Hans.md).

## Display badges with Liquid Glass

Badges provide people with a visual indicator of the activities they’ve recorded in the Landmarks app. When a person completes all four activities for a landmark, they earn that landmark’s badge. The sample uses custom Liquid Glass elements with badges, and shows how to coordinate animations with Liquid Glass.



To create a custom Liquid Glass badge, Landmarks uses a view with an `Image` to display a system symbol image for the badge. The badge has a background hexagon `Image` filled with a custom color. The badge view uses the [glassEffect(_:in:)](View/glassEffect___in.zh-Hans.md) modifier to apply Liquid Glass to the badge.

To demonstrate the morphing effect that the system provides with Liquid Glass animations, the sample organizes the badges and the toggle button into a [GlassEffectContainer](GlassEffectContainer.zh-Hans.md), and assigns each badge a unique [glassEffectID(_:in:)](View/glassEffectID___in.zh-Hans.md).

For more information, see [Landmarks-Displaying-custom-activity-badges](Landmarks-Displaying-custom-activity-badges.zh-Hans.md). For information about building custom views with Liquid Glass, see [Applying-Liquid-Glass-to-custom-views](Applying-Liquid-Glass-to-custom-views.zh-Hans.md).

## Create the app icon with Icon Composer

Landmarks includes a dynamic and expressive app icon composed in Icon Composer. You build app icons with four layers that the system uses to produce specular highlights when a person moves their device, so that the icon responds as if light was reflecting off the glass. The Settings app allows people to personalize the icon by selecting light, dark, clear, or tinted variants of your app icon as well.

For more information on creating a new app icon, see [doc://com.apple.documentation/documentation/Xcode/creating-your-app-icon-using-icon-composer].

For design guidance, see Human Interface Guidelines >  [doc://com.apple.documentation/design/Human-Interface-Guidelines/app-icons].

## App features

- **Landmarks: Applying a background extension effect**: Configure an image to blur and extend under a sidebar or inspector panel.
- **Landmarks: Extending horizontal scrolling under a sidebar or inspector**: Improve your horizontal scrollbar’s appearance by extending it under a sidebar or inspector.
- **Landmarks: Refining the system provided Liquid Glass effect in toolbars**: Organize toolbars into related groupings to improve their appearance and utility.
- **Landmarks: Displaying custom activity badges**: Provide people with a way to mark their adventures by displaying animated custom activity badges.

## Essentials

- **Adopting Liquid Glass**: Find out how to bring the new material to your app.
- **Learning SwiftUI**: Discover tips and techniques for building multiplatform apps with this set of conceptual articles and sample code.
- **Exploring SwiftUI Sample Apps**: Explore these SwiftUI samples using Swift Playgrounds on iPad or in Xcode to learn about defining user interfaces, responding to user interactions, and managing data flow.
- **SwiftUI updates**: Learn about important changes to SwiftUI.

