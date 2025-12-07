---
来源： https://developer.apple.com/documentation/swiftui/nshostingview
抓取时间： 2025-12-04T13:40:43Z
---

# NSHostingView

**Class**

承载 SwiftUI 视图层次结构的 AppKit 视图。

### 声明

```swift
@MainActor @preconcurrency class NSHostingView<Content> where Content : View
```

## 概览

您可以使用 `NSHostingView` 对象将 SwiftUI 视图集成到您的 AppKit 视图层次结构中。托管视图是管理单个 SwiftUI 视图的[doc://com.apple.documentation/documentation/AppKit/NSView] 对象，该视图本身可能包含其他 SwiftUI 视图。由于它是[doc://com.apple.documentation/documentation/AppKit/NSView] 对象，您可以将它集成到现有的 AppKit 视图层次结构中，以实现 UI 的一部分。例如，您可以使用托管视图来实现自定义控件。

托管视图是 SwiftUI 视图与 AppKit 界面之间的桥梁。在布局过程中，托管视图会向 AppKit 布局系统报告 SwiftUI 视图的内容大小偏好，以便适当调整视图大小。托管视图还会协调事件交付。

## 创建托管视图

- **init(rootView:)**：创建封装指定 SwiftUI 视图的托管视图对象。
- **init(coder:)**：从指定存档的内容创建托管视图对象。
- **prepareForReuse()**: 从指定的压缩包内容创建托管视图对象。

## 获取根视图

- **rootView**：由该视图控制器管理的 SwiftUI 视图层次结构的根视图。

## 配置视图布局行为

- **requiresConstraintBasedLayout**
- **userInterfaceLayoutDirection**
- **isFlipped**
- **layerContentsRedrawPolicy**
- **updateConstraints()**
- **layout()**
- **safeAreaRegions**：该视图控制器添加到其视图中的安全区域。

## 管理键盘交互

- **keyDown(with:)**：当用户在该视图处于响应链中时按下键盘上的一个键时调用。
- **keyUp(with:)**：当该视图在应答器链中时，用户松开键盘上的按键时调用。
- **performKeyEquivalent(with:)**：当用户在键盘上释放按键时调用。
- **insertText(_:)**
- **didChangeValue(forKey:)**
- **makeTouchBar()**

## 响应鼠标事件

- **mouseDown(with:)**
- **mouseUp(with:)**
- **otherMouseDown(with:)**
- **otherMouseUp(with:)**
- **rightMouseDown(with:)**
- **rightMouseUp(with:)**
- **mouseEntered(with:)**
- **mouseExited(with:)**
- **mouseDragged(with:)**
- **mouseMoved(with:)**
- **otherMouseDragged(with:)**
- **rightMouseDragged(with:)**
- **cursorUpdate(with:)**

## 响应触摸事件

- **touchesBegan(with:)**
- **touchesCancelled(with:)**
- **touchesEnded(with:)**
- **touchesMoved(with:)**

## 响应手势

- **magnify(with:)**
- **rotate(with:)**
- **scrollWheel(with:)**

## 处理拖放

- **validRequestor(forSendType:returnType:)**

## 提供上下文菜单

- **menu(for:)**

## 响应操作

- **responds(to:)**
- **forwardingTarget(for:)**
- **doCommand(by:)**

## 配置应答器行为

- **acceptsFirstResponder**
- **needsPanelToBecomeKey**

## 管理视图层次结构

- **viewWillMove(toWindow:)**
- **viewDidMoveToWindow()**
- **viewDidChangeBackingProperties()**
- **viewDidChangeEffectiveAppearance()**

## 修改矩形框架

- **intrinsicContentSize**
- **setFrameSize(_:)**
- **firstBaselineOffsetFromTop**
- **lastBaselineOffsetFromBottom**
- **sizingOptions**：托管视图如何根据其 SwiftUI 内容的大小创建和更新约束的选项。
- **firstTextLineCenter**：托管视图如何根据其 SwiftUI 内容的大小创建和更新约束的选项。

## 测试命中率

- **hitTest(_:)**

## 管理无障碍行为

- **accessibilityFocusedUIElement**
- **accessibilityChildren()**
- **accessibilityChildrenInNavigationOrder()**
- **accessibilityHitTest(_:)**
- **accessibilityRole()**
- **accessibilitySubrole()**
- **isAccessibilityElement()**

## 与 SwiftUI 桥接

- **sceneBridgingOptions**：该托管视图将管理窗口哪些方面的选项。

## 初始化程序

- **init(coder:rootView:)**：从归档文件和指定的 SwiftUI 视图创建托管视图对象。

## 实例属性

- **clipsToBounds**

## 实例方法

- **acceptsFirstMouse(for:)**
- **beginDocument()**
- **didAddSubview(_:)**
- **endDocument()**
- **observeValue(forKeyPath:of:change:context:)**
- **shouldDelayWindowOrdering(for:)**
- **showContextMenuForSelection(_:)**
- **viewDidEndLiveResize()**
- **viewWillStartLiveResize()**
- **willRemoveSubview(_:)**

## 在 AppKit 中显示 SwiftUI 视图

- 统一应用程序的动画**：在 SwiftUI、UIKit 和 AppKit 中创建一致的 UI 动画体验。
- **NSHostingController**：托管 SwiftUI 视图层次结构的 AppKit 视图控制器。
- **NSHostingMenu**：包含由 SwiftUI 视图定义的菜单项的 AppKit 菜单。
- **NSHostingSizingOptions**：关于托管视图和控制器如何将其内容的大小反映到自动布局约束中的选项。
- **NSHostingSceneRepresentation**：可托管和展示 SwiftUI 场景的 AppKit 类型
- **NSHostingSceneBridgingOptions**：托管视图和控制器如何管理相关窗口的选项。

## 继承自

- 视图

## 符合

- CVarArg
- 可复制
- 自定义调试字符串可转换
- 自定义字符串可转换
- 等价
- 可散列
- NSAccessibilityElementProtocol
- NSAccessibilityProtocol
- NSAnimatablePropertyContainer
- NSA 外观定制
- NSC 编码
- NSDraggingDestination
- NSDraggingSource
- NSO 对象协议
- NSS 标准键绑定响应
- NSTouchBarProvider
- NSUserActivityRestoring
- NSUserInterfaceItemIdentification
- NSUserInterfaceValidations


---
source: https://developer.apple.com/documentation/swiftui/nshostingview
crawled: 2025-12-04T13:40:43Z
---

# NSHostingView

**Class**

An AppKit view that hosts a SwiftUI view hierarchy.

## Declaration

```swift
@MainActor @preconcurrency class NSHostingView<Content> where Content : View
```

## Overview

You use `NSHostingView` objects to integrate SwiftUI views into your AppKit view hierarchies. A hosting view is an [doc://com.apple.documentation/documentation/AppKit/NSView] object that manages a single SwiftUI view, which may itself contain other SwiftUI views. Because it is an [doc://com.apple.documentation/documentation/AppKit/NSView] object, you can integrate it into your existing AppKit view hierarchies to implement portions of your UI. For example, you can use a hosting view to implement a custom control.

A hosting view acts as a bridge between your SwiftUI views and your AppKit interface. During layout, the hosting view reports the content size preferences of your SwiftUI views back to the AppKit layout system so that it can size the view appropriately. The hosting view also coordinates event delivery.

## Creating a hosting view

- **init(rootView:)**: Creates a hosting view object that wraps the specified SwiftUI view.
- **init(coder:)**: Creates a hosting view object from the contents of the specified archive.
- **prepareForReuse()**

## Getting the root view

- **rootView**: The root view of the SwiftUI view hierarchy managed by this view controller.

## Configuring the view layout behavior

- **requiresConstraintBasedLayout**
- **userInterfaceLayoutDirection**
- **isFlipped**
- **layerContentsRedrawPolicy**
- **updateConstraints()**
- **layout()**
- **safeAreaRegions**: The safe area regions that this view controller adds to its view.

## Managing keyboard interaction

- **keyDown(with:)**: Called when the user presses a key on the keyboard while this view is in the responder chain.
- **keyUp(with:)**: Called when the user releases a key on the keyboard while this view is in the responder chain.
- **performKeyEquivalent(with:)**
- **insertText(_:)**
- **didChangeValue(forKey:)**
- **makeTouchBar()**

## Responding to mouse events

- **mouseDown(with:)**
- **mouseUp(with:)**
- **otherMouseDown(with:)**
- **otherMouseUp(with:)**
- **rightMouseDown(with:)**
- **rightMouseUp(with:)**
- **mouseEntered(with:)**
- **mouseExited(with:)**
- **mouseDragged(with:)**
- **mouseMoved(with:)**
- **otherMouseDragged(with:)**
- **rightMouseDragged(with:)**
- **cursorUpdate(with:)**

## Responding to touch events

- **touchesBegan(with:)**
- **touchesCancelled(with:)**
- **touchesEnded(with:)**
- **touchesMoved(with:)**

## Responding to gestures

- **magnify(with:)**
- **rotate(with:)**
- **scrollWheel(with:)**

## Handling drag and drop

- **validRequestor(forSendType:returnType:)**

## Providing a context menu

- **menu(for:)**

## Responding to actions

- **responds(to:)**
- **forwardingTarget(for:)**
- **doCommand(by:)**

## Configuring the responder behavior

- **acceptsFirstResponder**
- **needsPanelToBecomeKey**

## Managing the view hierarchy

- **viewWillMove(toWindow:)**
- **viewDidMoveToWindow()**
- **viewDidChangeBackingProperties()**
- **viewDidChangeEffectiveAppearance()**

## Modifying the frame rectangle

- **intrinsicContentSize**
- **setFrameSize(_:)**
- **firstBaselineOffsetFromTop**
- **lastBaselineOffsetFromBottom**
- **sizingOptions**: The options for how the hosting view creates and updates constraints based on the size of its SwiftUI content.
- **firstTextLineCenter**

## Testing for hits

- **hitTest(_:)**

## Managing accessibility behaviors

- **accessibilityFocusedUIElement**
- **accessibilityChildren()**
- **accessibilityChildrenInNavigationOrder()**
- **accessibilityHitTest(_:)**
- **accessibilityRole()**
- **accessibilitySubrole()**
- **isAccessibilityElement()**

## Bridging with SwiftUI

- **sceneBridgingOptions**: The options for which aspects of the window will be managed by this hosting view.

## Initializers

- **init(coder:rootView:)**: Creates a hosting view object from an archive and the specified SwiftUI view.

## Instance Properties

- **clipsToBounds**

## Instance Methods

- **acceptsFirstMouse(for:)**
- **beginDocument()**
- **didAddSubview(_:)**
- **endDocument()**
- **observeValue(forKeyPath:of:change:context:)**
- **shouldDelayWindowOrdering(for:)**
- **showContextMenuForSelection(_:)**
- **viewDidEndLiveResize()**
- **viewWillStartLiveResize()**
- **willRemoveSubview(_:)**

## Displaying SwiftUI views in AppKit

- **Unifying your app’s animations**: Create a consistent UI animation experience across SwiftUI, UIKit, and AppKit.
- **NSHostingController**: An AppKit view controller that hosts SwiftUI view hierarchy.
- **NSHostingMenu**: An AppKit menu with menu items that are defined by a SwiftUI View.
- **NSHostingSizingOptions**: Options for how hosting views and controllers reflect their content’s size into Auto Layout constraints.
- **NSHostingSceneRepresentation**: An AppKit type that hosts and can present SwiftUI scenes
- **NSHostingSceneBridgingOptions**: Options for how hosting views and controllers manage aspects of the associated window.

## Inherits From

- NSView

## Conforms To

- CVarArg
- Copyable
- CustomDebugStringConvertible
- CustomStringConvertible
- Equatable
- Hashable
- NSAccessibilityElementProtocol
- NSAccessibilityProtocol
- NSAnimatablePropertyContainer
- NSAppearanceCustomization
- NSCoding
- NSDraggingDestination
- NSDraggingSource
- NSObjectProtocol
- NSStandardKeyBindingResponding
- NSTouchBarProvider
- NSUserActivityRestoring
- NSUserInterfaceItemIdentification
- NSUserInterfaceValidations

