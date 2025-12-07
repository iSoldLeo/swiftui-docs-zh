---
来源： https://developer.apple.com/documentation/SwiftUI/ToolbarItemPlacement/accessoryBar(id:)
抓取时间： 2025-12-03T06:03:12Z
---

# accessoryBar(id:)

**类型方法**

创建唯一的配件栏位置。

## 声明

```swift
@backDeployed(before: macOS 14.0)
static func accessoryBar<ID>(id: ID) -> ToolbarItemPlacement where ID : Hashable
```

## 参数

- **id**：该位置的唯一标识符。

## 讨论

在 macOS 上，带有附件栏位置的项目被放置在窗口标题栏和工具栏区域下方的一个部分。每个单独的标识符将对应于添加到该区域的一个单独的附件栏。

```swift
extension ToolbarItemPlacement {
    static let favoritesBar = accessoryBar(id: "com.example.favorites")
}
...
BrowserView()
    .toolbar {
        ToolbarItem(placement: .favoritesBar) {
            FavoritesBar()
        }
    }
```

## 获取明确的位置

- **topBarLeading**：将项目置于顶栏的前缘。
- **topBarTrailing**：将项目置于顶栏的后缘。
- **bottomBar**：将项目置于底部工具栏中。
- **bottomOrnament**：将项目置于窗口下方的装饰物中。
- **keyboard**：将项目置于键盘部分。


---
source: https://developer.apple.com/documentation/SwiftUI/ToolbarItemPlacement/accessoryBar(id:)
crawled: 2025-12-03T06:03:12Z
---

# accessoryBar(id:)

**Type Method**

Creates a unique accessory bar placement.

## Declaration

```swift
@backDeployed(before: macOS 14.0)
static func accessoryBar<ID>(id: ID) -> ToolbarItemPlacement where ID : Hashable
```

## Parameters

- **id**: A unique identifier for this placement.

## Discussion

On macOS, items with an accessory bar placement are placed in a section below the title bar and toolbar area of the window. Each separate identifier will correspond to a separate accessory bar that is added to this area.

```swift
extension ToolbarItemPlacement {
    static let favoritesBar = accessoryBar(id: "com.example.favorites")
}
...
BrowserView()
    .toolbar {
        ToolbarItem(placement: .favoritesBar) {
            FavoritesBar()
        }
    }
```

## Getting explicit placement

- **topBarLeading**: Places the item in the leading edge of the top bar.
- **topBarTrailing**: Places the item in the trailing edge of the top bar.
- **bottomBar**: Places the item in the bottom toolbar.
- **bottomOrnament**: Places the item in an ornament under the window.
- **keyboard**: The item is placed in the keyboard section.

