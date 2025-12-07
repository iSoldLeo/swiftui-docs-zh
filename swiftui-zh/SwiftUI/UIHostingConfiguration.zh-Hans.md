---
来源： https://developer.apple.com/documentation/SwiftUI/UIHostingConfiguration
抓取时间： 2025-12-02T17:44:53Z
---

# UIHostingConfiguration

**Structure**

适用于托管 SwiftUI 视图层次结构的内容配置。

## 声明

```swift
struct UIHostingConfiguration<Content, Background> where Content : View, Background : View
```

## 概览

使用符合[doc://com.apple.documentation/documentation/UIKit/UIContentConfiguration-9eib5] 协议的该类型值，再加上[doc://com.apple.documentation/documentation/UIKit/UICollectionViewCell] 或[doc://com.apple.documentation/documentation/UIKit/UITableViewCell]，可分别在集合或表视图中托管 SwiftUI 视图的层次结构。例如，下面显示的是一个堆栈，单元格内有图像和文本：

```swift
myCell.contentConfiguration = UIHostingConfiguration {
    HStack {
        Image(systemName: "star").foregroundStyle(.purple)
        Text("Favorites")
        Spacer()
    }
}
```

您还可以自定义包含单元格的背景。下面的示例绘制了蓝色背景：

```swift
myCell.contentConfiguration = UIHostingConfiguration {
    HStack {
        Image(systemName: "star").foregroundStyle(.purple)
        Text("Favorites")
        Spacer()
    }
}
.background {
    Color.blue
}
```

在列表布局中使用时，某些 API 会自动桥接，例如轻扫操作和分隔符对齐。下面的示例显示了一个拖尾黄色星形轻扫操作：

```swift
cell.contentConfiguration = UIHostingConfiguration {
    HStack {
        Image(systemName: "airplane")
        Text("Flight 123")
        Spacer()
    }
    .swipeActions {
        Button { ... } label: {
            Label("Favorite", systemImage: "star")
        }
        .tint(.yellow)
    }
}
```

## 创建和更新配置

- **init(content:)**：使用给定内容创建主机配置。

## 设置背景

- **background(_:)**：为主机配置的外层单元格设置背景内容。
- **background(content:)**：为主机配置的外层单元格设置背景内容。

## 设置边距

- **margins(_:_:)**：设置配置内容周围的边距。

## 设置大小

- **minSize(width:height:)**：设置配置的最小尺寸。
- **minSize()**：设置配置的最小尺寸。

## 在 UIKit 中显示 SwiftUI 视图

- 在 UIKit 中使用 SwiftUI**：了解如何将 SwiftUI 视图纳入 UIKit 应用程序。
- 统一应用程序的动画**：在 SwiftUI、UIKit 和 AppKit 中创建一致的 UI 动画体验。
- **UIHostingController**：管理 SwiftUI 视图层次结构的 UIKit 视图控制器。
- **UIHostingControllerSizingOptions**：托管控制器如何跟踪其内容大小的选项。
- **UIHostingSceneDelegate**：扩展了 `UIKit/UISceneDelegate` 以桥接 SwiftUI 场景。

## 符合

- UIContentConfiguration


---
source: https://developer.apple.com/documentation/SwiftUI/UIHostingConfiguration
crawled: 2025-12-02T17:44:53Z
---

# UIHostingConfiguration

**Structure**

A content configuration suitable for hosting a hierarchy of SwiftUI views.

## Declaration

```swift
struct UIHostingConfiguration<Content, Background> where Content : View, Background : View
```

## Overview

Use a value of this type, which conforms to the [doc://com.apple.documentation/documentation/UIKit/UIContentConfiguration-9eib5] protocol, with a [doc://com.apple.documentation/documentation/UIKit/UICollectionViewCell] or [doc://com.apple.documentation/documentation/UIKit/UITableViewCell] to host a hierarchy of SwiftUI views in a collection or table view, respectively. For example, the following shows a stack with an image and text inside the cell:

```swift
myCell.contentConfiguration = UIHostingConfiguration {
    HStack {
        Image(systemName: "star").foregroundStyle(.purple)
        Text("Favorites")
        Spacer()
    }
}
```

You can also customize the background of the containing cell. The following example draws a blue background:

```swift
myCell.contentConfiguration = UIHostingConfiguration {
    HStack {
        Image(systemName: "star").foregroundStyle(.purple)
        Text("Favorites")
        Spacer()
    }
}
.background {
    Color.blue
}
```

When used in a list layout, certain APIs are bridged automatically, like swipe actions and separator alignment. The following example shows a trailing yellow star swipe action:

```swift
cell.contentConfiguration = UIHostingConfiguration {
    HStack {
        Image(systemName: "airplane")
        Text("Flight 123")
        Spacer()
    }
    .swipeActions {
        Button { ... } label: {
            Label("Favorite", systemImage: "star")
        }
        .tint(.yellow)
    }
}
```

## Creating and updating a configuration

- **init(content:)**: Creates a hosting configuration with the given contents.

## Setting the background

- **background(_:)**: Sets the background contents for the hosting configuration’s enclosing cell.
- **background(content:)**: Sets the background contents for the hosting configuration’s enclosing cell.

## Setting margins

- **margins(_:_:)**: Sets the margins around the content of the configuration.

## Setting a size

- **minSize(width:height:)**: Sets the minimum size for the configuration.
- **minSize()**: Sets the minimum size for the configuration.

## Displaying SwiftUI views in UIKit

- **Using SwiftUI with UIKit**: Learn how to incorporate SwiftUI views into a UIKit app.
- **Unifying your app’s animations**: Create a consistent UI animation experience across SwiftUI, UIKit, and AppKit.
- **UIHostingController**: A UIKit view controller that manages a SwiftUI view hierarchy.
- **UIHostingControllerSizingOptions**: Options for how a hosting controller tracks its content’s size.
- **UIHostingSceneDelegate**: Extends `UIKit/UISceneDelegate` to bridge SwiftUI scenes.

## Conforms To

- UIContentConfiguration

