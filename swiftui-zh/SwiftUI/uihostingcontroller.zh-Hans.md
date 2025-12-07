---
来源： https://developer.apple.com/documentation/swiftui/uihostingcontroller
抓取时间： 2025-12-04T13:46:11Z
---

# UIHostingController

**Class**

管理 SwiftUI 视图层次结构的 UIKit 视图控制器。

## 声明

```swift
@MainActor @preconcurrency class UIHostingController<Content> where Content : View
```

## 概览

当您想将 SwiftUI 视图集成到 UIKit 视图层次结构中时，请创建`UIHostingController` 对象。创建时，指定要用作该视图控制器根视图的 SwiftUI 视图；以后可以使用 [rootView](UIHostingController/rootView.zh-Hans.md) 属性更改该视图。像使用其他视图控制器一样使用托管控制器，将其作为子视图控制器展示或嵌入到界面中。

## 创建托管控制器对象

- **init(rootView:)**：创建封装指定 SwiftUI 视图的托管控制器对象。
- **init(coder:rootView:)**：从归档和指定的 SwiftUI 视图创建托管控制器对象。
- **init(coder:)**：根据指定存档的内容创建托管控制器对象。

## 响应视图相关事件

- **loadView()**：从指定的存档内容创建托管控制器对象。
- **viewWillAppear(_:)**：通知视图控制器其视图即将添加到视图层次结构中。
- **viewDidAppear(_:)**：通知视图控制器其视图已被添加到视图层次结构中。
- **viewWillDisappear(_:)**：通知视图控制器其视图将从视图层次结构中移除。
- **viewDidDisappear(_:)**：通知视图控制器其视图将从视图层次结构中删除。
- **willMove(toParent:)**：通知视图控制器将其视图从视图层次结构中移除。
- **didMove(toParent:)**
- **viewWillTransition(to:with:)**
- **viewWillLayoutSubviews()**
- **target(forAction:withSender:)**
- **rootView**：由该视图控制器管理的 SwiftUI 视图层次结构的根视图。

## 检查模式

- **isModalInPresentation**

## 管理大小

- **sizingOptions**：托管控制器如何跟踪其 SwiftUI 内容大小变化的选项。
- **preferredContentSizeDidChange(forChildContentContainer:)**：托管控制器如何跟踪其 SwiftUI 内容大小变化的选项。
- **sizeThatFits(in:)**：计算并返回最适合当前视图的尺寸。
- **safeAreaRegions**：该视图控制器添加到其视图中的安全区域。

## 配置状态栏

- **preferredStatusBarStyle**：视图控制器首选的状态栏样式。
- **preferredStatusBarUpdateAnimation**：隐藏或显示该视图控制器的状态栏时要使用的动画样式。
- **prefersStatusBarHidden**：布尔值，表示视图控制器更喜欢隐藏还是显示状态栏。
- **childForStatusBarStyle**：布尔值。
- **childForStatusBarHidden**：一个布尔值，表示视图控制器是否喜欢隐藏或显示状态栏。

## 配置主页指示器

- **prefersHomeIndicatorAutoHidden**：布尔值，表示视图控制器希望隐藏还是显示主页指示符。
- **childForHomeIndicatorAutoHidden**：布尔值，表示视图控制器是否偏好隐藏或显示主页指示符。

## 配置界面外观

- **preferredUserInterfaceStyle**：此视图控制器的首选界面风格。
- **preferredScreenEdgesDeferringSystemGestures**：设置您希望手势优先于系统手势的屏幕边缘。
- **childForScreenEdgesDeferringSystemGestures**：设置您希望手势优先于系统手势的屏幕边缘。

## 访问可用的按键命令

- **keyCommands**

## 管理撤销

- **undoManager**

## 实例属性

- **childViewControllerForPreferredContainerBackgroundStyle**
- **preferredContainerBackgroundStyle**

## 实例方法

- **addChild(_:)**

## 在 UIKit 中显示 SwiftUI 视图

- 在 UIKit 中使用 SwiftUI**：了解如何将 SwiftUI 视图纳入 UIKit 应用程序。
- 统一应用程序的动画**：在 SwiftUI、UIKit 和 AppKit 中创建一致的 UI 动画体验。
- **UIHostingControllerSizingOptions**：关于托管控制器如何跟踪其内容大小的选项。
- **UIHostingConfiguration**：适合托管 SwiftUI 视图层次结构的内容配置。
- **UIHostingSceneDelegate**：扩展了 `UIKit/UISceneDelegate` 以桥接 SwiftUI 场景。

## 继承自

- UIViewController

## 符合

- CVarArg
- 可复制
- 自定义调试字符串可转换
- 自定义字符串可转换
- 等价
- Hashable
- NSC 编码
- NSExtensionRequestHandling
- NSO 对象协议
- NSTouchBarProvider
- UIActivityItemsConfigurationProviding
- UIAppearanceContainer
- UIContentContainer
- UIFocusEnvironment
- UIPasteConfigurationSupporting
- UIResponderStandardEditActions
- UIStateRestoring
- UITraitChangeObservable
- UITraitEnvironment
- UIUserActivityRestoring


---
source: https://developer.apple.com/documentation/swiftui/uihostingcontroller
crawled: 2025-12-04T13:46:11Z
---

# UIHostingController

**Class**

A UIKit view controller that manages a SwiftUI view hierarchy.

## Declaration

```swift
@MainActor @preconcurrency class UIHostingController<Content> where Content : View
```

## Overview

Create a `UIHostingController` object when you want to integrate SwiftUI views into a UIKit view hierarchy. At creation time, specify the SwiftUI view you want to use as the root view for this view controller; you can change that view later using the [rootView](UIHostingController/rootView.zh-Hans.md) property. Use the hosting controller like you would any other view controller, by presenting it or embedding it as a child view controller in your interface.

## Creating a hosting controller object

- **init(rootView:)**: Creates a hosting controller object that wraps the specified SwiftUI view.
- **init(coder:rootView:)**: Creates a hosting controller object from an archive and the specified SwiftUI view.
- **init(coder:)**: Creates a hosting controller object from the contents of the specified archive.

## Responding to view-related events

- **loadView()**
- **viewWillAppear(_:)**: Notifies the view controller that its view is about to be added to a view hierarchy.
- **viewDidAppear(_:)**: Notifies the view controller that its view has been added to a view hierarchy.
- **viewWillDisappear(_:)**: Notifies the view controller that its view will be removed from a view hierarchy.
- **viewDidDisappear(_:)**
- **willMove(toParent:)**
- **didMove(toParent:)**
- **viewWillTransition(to:with:)**
- **viewWillLayoutSubviews()**
- **target(forAction:withSender:)**
- **rootView**: The root view of the SwiftUI view hierarchy managed by this view controller.

## Checking for modality

- **isModalInPresentation**

## Managing the size

- **sizingOptions**: The options for how the hosting controller tracks changes to the size of its SwiftUI content.
- **preferredContentSizeDidChange(forChildContentContainer:)**
- **sizeThatFits(in:)**: Calculates and returns the most appropriate size for the current view.
- **safeAreaRegions**: The safe area regions that this view controller adds to its view.

## Configuring the status bar

- **preferredStatusBarStyle**: The preferred status bar style for the view controller.
- **preferredStatusBarUpdateAnimation**: The animation style to use when hiding or showing the status bar for this view controller.
- **prefersStatusBarHidden**: A Boolean value that indicates whether the view controller prefers the status bar to be hidden or shown.
- **childForStatusBarStyle**
- **childForStatusBarHidden**

## Configuring the home indicator

- **prefersHomeIndicatorAutoHidden**: A Boolean value that indicates whether the view controller prefers the home indicator to be hidden or shown.
- **childForHomeIndicatorAutoHidden**

## Configuring the interface appearance

- **preferredUserInterfaceStyle**: The preferred interface style for this view controller.
- **preferredScreenEdgesDeferringSystemGestures**: Sets the screen edge from which you want your gesture to take precedence over the system gesture.
- **childForScreenEdgesDeferringSystemGestures**

## Accessing the available key commands

- **keyCommands**

## Managing undo

- **undoManager**

## Instance Properties

- **childViewControllerForPreferredContainerBackgroundStyle**
- **preferredContainerBackgroundStyle**

## Instance Methods

- **addChild(_:)**

## Displaying SwiftUI views in UIKit

- **Using SwiftUI with UIKit**: Learn how to incorporate SwiftUI views into a UIKit app.
- **Unifying your app’s animations**: Create a consistent UI animation experience across SwiftUI, UIKit, and AppKit.
- **UIHostingControllerSizingOptions**: Options for how a hosting controller tracks its content’s size.
- **UIHostingConfiguration**: A content configuration suitable for hosting a hierarchy of SwiftUI views.
- **UIHostingSceneDelegate**: Extends `UIKit/UISceneDelegate` to bridge SwiftUI scenes.

## Inherits From

- UIViewController

## Conforms To

- CVarArg
- Copyable
- CustomDebugStringConvertible
- CustomStringConvertible
- Equatable
- Hashable
- NSCoding
- NSExtensionRequestHandling
- NSObjectProtocol
- NSTouchBarProvider
- UIActivityItemsConfigurationProviding
- UIAppearanceContainer
- UIContentContainer
- UIFocusEnvironment
- UIPasteConfigurationSupporting
- UIResponderStandardEditActions
- UIStateRestoring
- UITraitChangeObservable
- UITraitEnvironment
- UIUserActivityRestoring

