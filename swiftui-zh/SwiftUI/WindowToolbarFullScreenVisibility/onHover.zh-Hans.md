--- 来源：https://developer.apple.com/documentation/SwiftUI/WindowToolbarFullScreenVisibility/onHover

抓取时间：2025-12-03T05:32:29Z

---

# onHover

**类型属性**

默认情况下，在全屏模式下隐藏窗口工具栏。当鼠标移动到菜单栏所在的区域时，工具栏才会显示。

## 声明

```swift
static let onHover: WindowToolbarFullScreenVisibility
```

## 讨论

如果工具栏完全隐藏，则此属性无效。例如，如果使用 [toolbarVisibility(_:for:)](../View/toolbarVisibility___for.zh-Hans.md) 将 `windowToolbar` 位置的可见性设置为 `hidden`，则工具栏即使在全屏模式下也仍然完全隐藏。


---
source: https://developer.apple.com/documentation/SwiftUI/WindowToolbarFullScreenVisibility/onHover
crawled: 2025-12-03T05:32:29Z
---

# onHover

**Type Property**

Hide the window toolbar in full screen mode by default. It will reveal itself when the mouse moves into the area occupied by the menu bar.

## Declaration

```swift
static let onHover: WindowToolbarFullScreenVisibility
```

## Discussion

This has no effect if the toolbar is completely hidden, i.e. setting the visibility to `hidden` for `windowToolbar` placements using [toolbarVisibility(_:for:)](../View/toolbarVisibility___for.zh-Hans.md) will cause the toolbar to remain completely hidden, even in full screen.

