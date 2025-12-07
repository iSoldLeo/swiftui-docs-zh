---
来源： https://developer.apple.com/documentation/SwiftUI/Landmarks-Refining-the-system-provided-glass-effect-in-toolbars
抓取时间： 2025-12-02T15:45:39Z
---

# 地标：完善系统提供的工具栏液态玻璃效果

** 示例代码**

将工具栏组织成相关分组，以改善其外观和实用性。

## 概览

地标应用程序可让人们探索世界各地有趣的景点。无论是家附近的国家公园，还是不同大洲的遥远地点，该应用程序都能让人们组织和标记自己的探险活动，并在途中获得自定义活动徽章。

本示例演示了如何在工具栏中完善系统提供的玻璃效果。在`LandmarkDetailView`中，示例添加了以下工具栏项目：

- 共享地标
- 从收藏列表中添加或删除地标
- 从收藏中添加或删除地标
- 显示或隐藏检查器

系统会自动将 Liquid Glass 应用于工具栏项目。



## 将工具栏项目按逻辑分组

为了将工具栏项目按逻辑分组，示例添加了 [ToolbarSpacer](ToolbarSpacer.zh-Hans.md) 项目，并通过 [fixed](SpacerSizing/fixed.zh-Hans.md) 作为 `sizing` 参数，将工具栏划分为多个部分：

```swift
.toolbar {
    ToolbarSpacer(.flexible)

    ToolbarItem {
        ShareLink(item: landmark, preview: landmark.sharePreview)
    }

    ToolbarSpacer(.fixed)
    
    ToolbarItemGroup {
        LandmarkFavoriteButton(landmark: landmark)
        LandmarkCollectionsMenu(landmark: landmark)
    }
    
    ToolbarSpacer(.fixed)

    ToolbarItem {
        Button("Info", systemImage: "info") {
            modelData.selectedLandmark = landmark
            modelData.isLandmarkInspectorPresented.toggle()
        }
    }
}
```

## 应用程序功能

- **地标：应用背景扩展效果**：配置图像，使其在侧边栏或检查面板下模糊并延伸。
- **地标在侧边栏或检查器下扩展水平滚动条**：通过在侧边栏或检查器下扩展横向滚动条来改善横向滚动条的外观。
- **地标显示自定义活动徽章**：通过显示动画自定义活动徽章，为用户提供一种标记其冒险经历的方式。


---
source: https://developer.apple.com/documentation/SwiftUI/Landmarks-Refining-the-system-provided-glass-effect-in-toolbars
crawled: 2025-12-02T15:45:39Z
---

# Landmarks: Refining the system provided Liquid Glass effect in toolbars

**Sample Code**

Organize toolbars into related groupings to improve their appearance and utility.

## Overview

The Landmarks app lets people explore interesting sites around the world. Whether it’s a national park near their home or a far-flung location on a different continent, the app provides a way for people to organize and mark their adventures and receive custom activity badges along the way.

This sample demonstrates how to refine the system provided glass effect in toolbars. In `LandmarkDetailView`, the sample adds toolbar items for:

- sharing a landmark
- adding or removing a landmark from a list of Favorites
- adding or removing a landmark from Collections
- showing or hiding the inspector

The system applies Liquid Glass to the toolbar items automatically.



## Organize the toolbar items into logical groupings

To organize the toolbar items into logical groupings, the sample adds [ToolbarSpacer](ToolbarSpacer.zh-Hans.md) items and passes [fixed](SpacerSizing/fixed.zh-Hans.md) as the `sizing` parameter to divide the toolbar into sections:

```swift
.toolbar {
    ToolbarSpacer(.flexible)

    ToolbarItem {
        ShareLink(item: landmark, preview: landmark.sharePreview)
    }

    ToolbarSpacer(.fixed)
    
    ToolbarItemGroup {
        LandmarkFavoriteButton(landmark: landmark)
        LandmarkCollectionsMenu(landmark: landmark)
    }
    
    ToolbarSpacer(.fixed)

    ToolbarItem {
        Button("Info", systemImage: "info") {
            modelData.selectedLandmark = landmark
            modelData.isLandmarkInspectorPresented.toggle()
        }
    }
}
```

## App features

- **Landmarks: Applying a background extension effect**: Configure an image to blur and extend under a sidebar or inspector panel.
- **Landmarks: Extending horizontal scrolling under a sidebar or inspector**: Improve your horizontal scrollbar’s appearance by extending it under a sidebar or inspector.
- **Landmarks: Displaying custom activity badges**: Provide people with a way to mark their adventures by displaying animated custom activity badges.

