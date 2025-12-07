---
来源： https://developer.apple.com/documentation/SwiftUI/ToolbarPlacement/accessoryBar(id:)
抓取时间： 2025-12-01T10:54:03Z
---

# accessoryBar(id:)

**类型方法**

创建唯一的配件栏位置。

## 声明

```swift
@backDeployed(before: macOS 14.0)
static func accessoryBar<ID>(id: ID) -> ToolbarPlacement where ID : Hashable
```

## 参数

- **id**：该位置的唯一标识符。

## 讨论

在 macOS 上，附件栏位于窗口标题栏和工具栏区域的下方。每个单独的标识符将对应于添加到该区域的一个单独的附件栏。

对于使用具有相同标识符的自定义[ToolbarItemPlacement](../ToolbarItemPlacement.zh-Hans.md)的项目，可使用自定义位置来控制包含栏的外观。

```swift
private let favoritesBarID = "com.example.favoritesBar"
extension ToolbarItemPlacement {
    static let favoritesBar = accessoryBar(id: favoritesBarID)
}
extension ToolbarPlacement {
    static let favoritesBar = accessoryBar(id: favoritesBarID)
}
...
BrowserView()
    .toolbar {
        ToolbarItem(placement: .favoritesBar) {
            FavoritesBar()
        }
    }
    .toolbar(.hidden, for: .favoritesBar)
```

## 获取位置

- **automatic**：主工具栏。
- **bottomBar**：应用程序的底部工具栏。
- **bottomOrnament**：应用程序的底部工具栏：应用程序的底部装饰。
- **navigationBar**：应用程序的导航栏。
- **tabBar**：应用程序的导航栏：应用程序的标签栏。
- **windowToolbar**：应用程序的标签栏：包含窗口的工具栏的位置，有时也称为标题栏。


---
source: https://developer.apple.com/documentation/SwiftUI/ToolbarPlacement/accessoryBar(id:)
crawled: 2025-12-01T10:54:03Z
---

# accessoryBar(id:)

**Type Method**

Creates a unique accessory bar placement.

## Declaration

```swift
@backDeployed(before: macOS 14.0)
static func accessoryBar<ID>(id: ID) -> ToolbarPlacement where ID : Hashable
```

## Parameters

- **id**: A unique identifier for this placement.

## Discussion

On macOS, accessory bars are in a section below the title bar and toolbar area of the window. Each separate identifier will correspond to a separate accessory bar that is added to this area.

Use a custom placement to control the appearance of the containing bar for items using a custom [ToolbarItemPlacement](../ToolbarItemPlacement.zh-Hans.md) with the same identifier.

```swift
private let favoritesBarID = "com.example.favoritesBar"
extension ToolbarItemPlacement {
    static let favoritesBar = accessoryBar(id: favoritesBarID)
}
extension ToolbarPlacement {
    static let favoritesBar = accessoryBar(id: favoritesBarID)
}
...
BrowserView()
    .toolbar {
        ToolbarItem(placement: .favoritesBar) {
            FavoritesBar()
        }
    }
    .toolbar(.hidden, for: .favoritesBar)
```

## Getting placements

- **automatic**: The primary toolbar.
- **bottomBar**: The bottom toolbar of an app.
- **bottomOrnament**: The bottom ornament of an app.
- **navigationBar**: The navigation bar of an app.
- **tabBar**: The tab bar of an app.
- **windowToolbar**: The placement for the containing window’s toolbar, sometimes referred to as the titlebar.

