--- 来源：https://developer.apple.com/documentation/SwiftUI/NavigationView
抓取时间：2025-12-02T17:27:33Z

---

# NavigationView

**Structure**

用于呈现视图堆栈的视图，该堆栈代表导航层级结构中的可见路径。

## 声明

```swift
struct NavigationView<Content> where Content : View
```

## 概述

使用 `NavigationView` 创建一个基于导航的应用，用户可以在其中浏览视图集合。用户通过选择您提供的 [NavigationLink](NavigationLink.zh-Hans.md) 来导航到目标视图。在 iPadOS 和 macOS 上，目标内容显示在下一列。其他平台会将新视图推送到堆栈中，并允许使用平台特定的控件（例如“返回”按钮或滑动操作）从堆栈中移除项目。

使用 [init(content:)](NavigationView/init_content.zh-Hans.md) 初始化器创建导航视图，该视图直接关联导航链接及其目标视图：

```swift
NavigationView {
    List(model.notes) { note in
        NavigationLink(note.title, destination: NoteEditor(id: note.id))
    }
    Text("Select a Note")
}
```

使用 [navigationViewStyle(_:)](View/navigationViewStyle.zh-Hans.md) 视图修饰符修改导航视图，即可设置其样式。对导航视图呈现的视图使用其他修饰符（例如 [doc://com.apple.SwiftUI/documentation/SwiftUI/View/navigationTitle(_:)-avgj]），可以自定义呈现视图的导航界面。

## 创建导航视图

- **init(content:)**：创建基于目标的导航视图。

## 设置导航视图样式

- **navigationViewStyle(_:)**：设置此视图中导航视图的样式。

- **NavigationViewStyle**：导航视图的外观和交互规范。

## 已弃用类型

- **tabItem(_:)**：设置与此视图关联的选项卡栏项。

## 符合以下规范

- View


---
source: https://developer.apple.com/documentation/SwiftUI/NavigationView
crawled: 2025-12-02T17:27:33Z
---

# NavigationView

**Structure**

A view for presenting a stack of views that represents a visible path in a navigation hierarchy.

## Declaration

```swift
struct NavigationView<Content> where Content : View
```

## Overview

Use a `NavigationView` to create a navigation-based app in which the user can traverse a collection of views. Users navigate to a destination view by selecting a [NavigationLink](NavigationLink.zh-Hans.md) that you provide. On iPadOS and macOS, the destination content appears in the next column. Other platforms push a new view onto the stack, and enable removing items from the stack with platform-specific controls, like a Back button or a swipe gesture.



Use the [init(content:)](NavigationView/init_content.zh-Hans.md) initializer to create a navigation view that directly associates navigation links and their destination views:

```swift
NavigationView {
    List(model.notes) { note in
        NavigationLink(note.title, destination: NoteEditor(id: note.id))
    }
    Text("Select a Note")
}
```

Style a navigation view by modifying it with the [navigationViewStyle(_:)](View/navigationViewStyle.zh-Hans.md) view modifier. Use other modifiers, like [doc://com.apple.SwiftUI/documentation/SwiftUI/View/navigationTitle(_:)-avgj], on views presented by the navigation view to customize the navigation interface for the presented view.

## Creating a navigation view

- **init(content:)**: Creates a destination-based navigation view.

## Styling navigation views

- **navigationViewStyle(_:)**: Sets the style for navigation views within this view.
- **NavigationViewStyle**: A specification for the appearance and interaction of a navigation view.

## Deprecated Types

- **tabItem(_:)**: Sets the tab bar item associated with this view.

## Conforms To

- View

