---
来源： https://developer.apple.com/documentation/SwiftUI/Landmarks-Extending-horizontal-scrolling-under-a-sidebar-or-inspector
抓取时间： 2025-12-02T15:45:38Z
---

# 地标：在侧边栏或检查器下扩展水平滚动

** 示例代码**

在侧边栏或检查器下扩展水平滚动条，改善其外观。

## 概览

地标应用程序可让人们探索世界各地有趣的景点。无论是家附近的国家公园，还是不同大洲的遥远地点，该应用程序都能让人们组织和标记自己的探险活动，并在途中获得自定义活动徽章。

本示例演示了如何在侧边栏或检查器下扩展水平滚动。在`LandmarksView`的每个大陆部分中，`LandmarkHorizontalListView`的实例显示了一个水平滚动的地标视图列表。打开时，地标视图可在侧边栏或检查器下方滚动。



## 配置滚动视图

为了达到这种效果，示例配置了`LandmarkHorizontalListView`，使其触及前缘和后缘。当滚动视图触及侧边栏或检查器时，系统会自动将其调整为在侧边栏或检查器下方滚动，然后离开屏幕边缘。

示例在[Spacer](Spacer.zh-Hans.md)的开头添加了[ScrollView](ScrollView.zh-Hans.md)，以嵌入内容，使其与标题填充对齐：

```swift
ScrollView(.horizontal, showsIndicators: false) {
    LazyHStack(spacing: Constants.standardPadding) {
        Spacer()
            .frame(width: Constants.standardPadding)
        ForEach(landmarkList) { landmark in
            //...
        }
    }
}
```

## 应用程序功能

- **地标：应用背景扩展效果**：配置图像，使其在侧边栏或检查面板下模糊并延伸。
- **地标完善系统提供的工具栏液体玻璃效果**：将工具栏组织成相关分组，以改善其外观和实用性。
- **地标显示自定义活动徽章**：通过显示动画自定义活动徽章，为用户提供一种标记其冒险经历的方式。


---
source: https://developer.apple.com/documentation/SwiftUI/Landmarks-Extending-horizontal-scrolling-under-a-sidebar-or-inspector
crawled: 2025-12-02T15:45:38Z
---

# Landmarks: Extending horizontal scrolling under a sidebar or inspector

**Sample Code**

Improve your horizontal scrollbar’s appearance by extending it under a sidebar or inspector.

## Overview

The Landmarks app lets people explore interesting sites around the world. Whether it’s a national park near their home or a far-flung location on a different continent, the app provides a way for people to organize and mark their adventures and receive custom activity badges along the way.

This sample demonstrates how to extend horizontal scrolling under a sidebar or inspector. Within each continent section in `LandmarksView`, an instance of `LandmarkHorizontalListView` shows a horizontally scrolling list of landmark views. When open, the landmark views can scroll underneath the sidebar or inspector.



## Configure the scroll view

To achieve this effect, the sample configures the `LandmarkHorizontalListView` so it touches the leading and trailing edges. When a scroll view touches the sidebar or inspector, the system automatically adjusts it to scroll under the sidebar or inspector and then off the edge of the screen.

The sample adds a [Spacer](Spacer.zh-Hans.md) at the beginning of the [ScrollView](ScrollView.zh-Hans.md) to inset the content so it aligns with the title padding:

```swift
ScrollView(.horizontal, showsIndicators: false) {
    LazyHStack(spacing: Constants.standardPadding) {
        Spacer()
            .frame(width: Constants.standardPadding)
        ForEach(landmarkList) { landmark in
            //...
        }
    }
}
```

## App features

- **Landmarks: Applying a background extension effect**: Configure an image to blur and extend under a sidebar or inspector panel.
- **Landmarks: Refining the system provided Liquid Glass effect in toolbars**: Organize toolbars into related groupings to improve their appearance and utility.
- **Landmarks: Displaying custom activity badges**: Provide people with a way to mark their adventures by displaying animated custom activity badges.

