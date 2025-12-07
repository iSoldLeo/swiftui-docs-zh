--- 来源：https://developer.apple.com/documentation/SwiftUI/NSHostingMenu

抓取时间：2025-12-02T17:44:42Z

---

# NSHostingMenu

**Class**

一个 AppKit 菜单，其菜单项由 SwiftUI 视图定义。

## 声明

```swift
class NSHostingMenu<Content> where Content : View
```

## 概述

由于 `NSHostingMenu` 是 `NSMenu` 的子类，您可以将其集成到现有的显示菜单的 AppKit 视图层级结构中。例如，您可以将宿主菜单设置为 AppKit 视图的上下文菜单。

宿主菜单的 `items` 属性将根据提供的 `rootView` 的内容进行更新，因此不允许直接修改菜单项数组，即使使用菜单本身的 `addItem` 等方法也不行。

菜单中托管的 SwiftUI 视图的样式和行为将与 [Menu](Menu.zh-Hans.md) 或 `View/contextMenu` 中的视图完全相同。请确保使用 `Group` 或包含多个子视图的视图作为顶级容器，而不是 `HStack` 或其他试图将所有操作放在单个菜单项中的容器。

例如，以下代码将设置 Finder 上下文菜单的第一部分，该菜单既会显示在工具栏的“操作”按钮中，也会显示在上下文菜单中：

```swift
struct FileOrFolderContextMenu: View {
    let url: URL
    var body: some View {
        Section {
            if url.hasDirectoryPath {
                Button("Open in New Tab") { ... }
            } else {
                Button("Open") { ... }
                Menu("Open With") { ... }
            }
        }
        Section {
            Button("Move to Trash") { ... }
        }
        Section {
            Button("Get Info") { ... }
            Button("Rename") { ... }
            if url.pathExtension != "zip" {
                Button("Compress “\(url.lastPathComponent)”") { ... }
            }
            // ...
        }
    }
}

// In the toolbar setup:
let popUpButton = NSPopUpButton(frame: .zero, pullsDown: true)
(popUpButton.cell as! NSPopUpButtonCell).usesItemFromMenu = false
popUpButton.menu = NSHostingMenu(rootView: Group {
    Button("New Folder") { ... }
    FileOrFolderContextMenu(url: selectedURL)
})

// In the column view:
List(directoryContents, selection: $selection) { entry in
    DirectoryEntryRow(entry: entry)
        .contextMenu {
            FileOrFolderContextMenu(url: entry.url)
        }
}
```

## 初始化器

- **init(rootView:)**：创建一个包含指定 SwiftUI 视图的宿主菜单对象。

## 实例属性

- **rootView**：此菜单管理的 SwiftUI 视图层次结构的根视图。

## 在 AppKit 中显示 SwiftUI 视图

- **统一应用的动画**：在 SwiftUI、UIKit 和 AppKit 中创建一致的 UI 动画体验。

- **NSHostingController**：一个包含 SwiftUI 视图层次结构的 AppKit 视图控制器。

- **NSHostingView**：一个包含 SwiftUI 视图层次结构的 AppKit 视图。

- **NSHostingSizingOptions**：用于设置宿主视图和控制器如何将其内容大小反映到自动布局约束中的选项。

- **NSHostingSceneRepresentation**：用于托管和呈现 SwiftUI 场景的 AppKit 类型。

- **NSHostingSceneBridgingOptions**：用于设置宿主视图和控制器如何管理关联窗口的选项。

## 继承自

- NSMenu

## 遵循以下协议

- CVarArg

- CustomDebugStringConvertible

- CustomStringConvertible

- Equatable

- Hashable

- NSAccessibilityElementProtocol

- NSAccessibilityProtocol

- NSAppearanceCustomization

- NSCoding

- NSCopying

- NSObjectProtocol

- NSUserInterfaceItemIdentification


---
source: https://developer.apple.com/documentation/SwiftUI/NSHostingMenu
crawled: 2025-12-02T17:44:42Z
---

# NSHostingMenu

**Class**

An AppKit menu with menu items that are defined by a SwiftUI View.

## Declaration

```swift
class NSHostingMenu<Content> where Content : View
```

## Overview

Because `NSHostingMenu` is an `NSMenu` subclass, you can integrate it into your existing AppKit view hierarchies that display menus. For example, you can set a hosting menu as an AppKit view’s context menu.

A hosting menu’s `items` property will be updated based on the content of the provided `rootView`, so direct mutations to the item array are not allowed, even if done using methods like `addItem` on the menu itself.

SwiftUI views hosted in the menu will be styled and behave identically to views in a [Menu](Menu.zh-Hans.md) or `View/contextMenu`. Make sure to use a `Group` or a view with multiple subviews as your top level container instead of an `HStack` or other container that would attempt to place all of your actions in a single menu item.



For example, the following code would set up the first part of the Finder’s context menu, both in the Action button in the toolbar and as a context menu:

```swift
struct FileOrFolderContextMenu: View {
    let url: URL
    var body: some View {
        Section {
            if url.hasDirectoryPath {
                Button("Open in New Tab") { ... }
            } else {
                Button("Open") { ... }
                Menu("Open With") { ... }
            }
        }
        Section {
            Button("Move to Trash") { ... }
        }
        Section {
            Button("Get Info") { ... }
            Button("Rename") { ... }
            if url.pathExtension != "zip" {
                Button("Compress “\(url.lastPathComponent)”") { ... }
            }
            // ...
        }
    }
}

// In the toolbar setup:
let popUpButton = NSPopUpButton(frame: .zero, pullsDown: true)
(popUpButton.cell as! NSPopUpButtonCell).usesItemFromMenu = false
popUpButton.menu = NSHostingMenu(rootView: Group {
    Button("New Folder") { ... }
    FileOrFolderContextMenu(url: selectedURL)
})

// In the column view:
List(directoryContents, selection: $selection) { entry in
    DirectoryEntryRow(entry: entry)
        .contextMenu {
            FileOrFolderContextMenu(url: entry.url)
        }
}
```

## Initializers

- **init(rootView:)**: Creates a hosting menu object that wraps the specified SwiftUI view.

## Instance Properties

- **rootView**: The root view of the SwiftUI view hierarchy managed by this menu.

## Displaying SwiftUI views in AppKit

- **Unifying your app’s animations**: Create a consistent UI animation experience across SwiftUI, UIKit, and AppKit.
- **NSHostingController**: An AppKit view controller that hosts SwiftUI view hierarchy.
- **NSHostingView**: An AppKit view that hosts a SwiftUI view hierarchy.
- **NSHostingSizingOptions**: Options for how hosting views and controllers reflect their content’s size into Auto Layout constraints.
- **NSHostingSceneRepresentation**: An AppKit type that hosts and can present SwiftUI scenes
- **NSHostingSceneBridgingOptions**: Options for how hosting views and controllers manage aspects of the associated window.

## Inherits From

- NSMenu

## Conforms To

- CVarArg
- CustomDebugStringConvertible
- CustomStringConvertible
- Equatable
- Hashable
- NSAccessibilityElementProtocol
- NSAccessibilityProtocol
- NSAppearanceCustomization
- NSCoding
- NSCopying
- NSObjectProtocol
- NSUserInterfaceItemIdentification

