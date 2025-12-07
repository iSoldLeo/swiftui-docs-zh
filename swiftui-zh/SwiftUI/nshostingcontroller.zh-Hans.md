---
来源： https://developer.apple.com/documentation/swiftui/nshostingcontroller
抓取时间： 2025-12-04T13:40:39Z
---

# NSHostingController

**Class**

用于托管 SwiftUI 视图层次结构的 AppKit 视图控制器。

### 声明

```swift
@MainActor @preconcurrency class NSHostingController<Content> where Content : View
```

## 概览

当您要将 SwiftUI 视图集成到 AppKit 视图层次结构中时，请创建`NSHostingController` 对象。创建时，指定要用作该视图控制器根视图的 SwiftUI 视图；以后可以使用 [rootView](NSHostingController/rootView.zh-Hans.md) 属性更改该视图。像使用其他视图控制器一样使用托管控制器，将其作为子视图控制器展示或嵌入到界面中。

## 创建托管控制器对象

- **init(rootView:)**：创建封装指定 SwiftUI 视图的托管控制器对象。
- **init(coder:rootView:)**：从归档和指定的 SwiftUI 视图创建托管控制器对象。
- **init(coder:)**：根据指定存档的内容创建托管控制器对象。

## 获取根视图

- **rootView**：由该视图控制器管理的 SwiftUI 视图层次结构的根视图。
- **identifier**：该视图控制器管理的 SwiftUI 视图层次结构的根视图。

## 配置控制器

- **sizeThatFits(in:)**：计算并返回最适合当前视图的尺寸。
- **preferredContentSize**：计算并返回当前视图最合适的尺寸。
- **sizingOptions**：托管控制器视图如何根据 SwiftUI 内容的大小创建和更新约束的选项。
- **safeAreaRegions**：该视图控制器添加到其视图的安全区域。
- **sceneBridgingOptions**：窗口的哪些方面将由此控制器的托管视图管理的选项。

## 在 AppKit 中显示 SwiftUI 视图

- 统一应用程序的动画**：在 SwiftUI、UIKit 和 AppKit 中创建一致的 UI 动画体验。
- **NSHostingView**：承载 SwiftUI 视图层次结构的 AppKit 视图。
- **NSHostingMenu**：包含由 SwiftUI 视图定义的菜单项的 AppKit 菜单。
- **NSHostingSizingOptions**：关于托管视图和控制器如何将其内容的大小反映到自动布局约束中的选项。
- **NSHostingSceneRepresentation**：可托管和展示 SwiftUI 场景的 AppKit 类型
- **NSHostingSceneBridgingOptions**：托管视图和控制器如何管理相关窗口的选项。

## 继承自

- 视图控制器

## 符合

- CVarArg
- 自定义调试字符串可转换
- 自定义字符串可转换
- 等价
- 可散列
- NSCoding
- NSEditor
- NSExtensionRequestHandling
- NSO 对象协议
- NSSeguePerforming
- NSS 标准键绑定响应
- NSTouchBarProvider
- NSUserActivityRestoring
- NSUserInterfaceItemIdentification


---
source: https://developer.apple.com/documentation/swiftui/nshostingcontroller
crawled: 2025-12-04T13:40:39Z
---

# NSHostingController

**Class**

An AppKit view controller that hosts SwiftUI view hierarchy.

## Declaration

```swift
@MainActor @preconcurrency class NSHostingController<Content> where Content : View
```

## Overview

Create an `NSHostingController` object when you want to integrate SwiftUI views into an AppKit view hierarchy. At creation time, specify the SwiftUI view you want to use as the root view for this view controller; you can change that view later using the [rootView](NSHostingController/rootView.zh-Hans.md) property. Use the hosting controller like you would any other view controller, by presenting it or embedding it as a child view controller in your interface.

## Creating a hosting controller object

- **init(rootView:)**: Creates a hosting controller object that wraps the specified SwiftUI view.
- **init(coder:rootView:)**: Creates a hosting controller object from an archive and the specified SwiftUI view.
- **init(coder:)**: Creates a hosting controller object from the contents of the specified archive.

## Getting the root view

- **rootView**: The root view of the SwiftUI view hierarchy managed by this view controller.
- **identifier**

## Configuring the controller

- **sizeThatFits(in:)**: Calculates and returns the most appropriate size for the current view.
- **preferredContentSize**
- **sizingOptions**: The options for how the hosting controller’s view creates and updates constraints based on the size of its SwiftUI content.
- **safeAreaRegions**: The safe area regions that this view controller adds to its view.
- **sceneBridgingOptions**: The options for which aspects of the window will be managed by this controller’s hosting view.

## Displaying SwiftUI views in AppKit

- **Unifying your app’s animations**: Create a consistent UI animation experience across SwiftUI, UIKit, and AppKit.
- **NSHostingView**: An AppKit view that hosts a SwiftUI view hierarchy.
- **NSHostingMenu**: An AppKit menu with menu items that are defined by a SwiftUI View.
- **NSHostingSizingOptions**: Options for how hosting views and controllers reflect their content’s size into Auto Layout constraints.
- **NSHostingSceneRepresentation**: An AppKit type that hosts and can present SwiftUI scenes
- **NSHostingSceneBridgingOptions**: Options for how hosting views and controllers manage aspects of the associated window.

## Inherits From

- NSViewController

## Conforms To

- CVarArg
- CustomDebugStringConvertible
- CustomStringConvertible
- Equatable
- Hashable
- NSCoding
- NSEditor
- NSExtensionRequestHandling
- NSObjectProtocol
- NSSeguePerforming
- NSStandardKeyBindingResponding
- NSTouchBarProvider
- NSUserActivityRestoring
- NSUserInterfaceItemIdentification

