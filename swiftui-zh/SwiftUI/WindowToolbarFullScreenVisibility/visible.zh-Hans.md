--- 来源：https://developer.apple.com/documentation/SwiftUI/WindowToolbarFullScreenVisibility/visible

抓取时间：2025-12-03T05:32:30Z

---

# visible

**类型属性**

在窗口处于全屏模式时，优先显示窗口工具栏。

## 声明

```swift
static let visible: WindowToolbarFullScreenVisibility
```

## 讨论

如果工具栏完全隐藏，则此属性无效。例如，对于使用 [toolbarVisibility(_:for:)](../View/toolbarVisibility___for.zh-Hans.md) 的 `windowToolbar` 位置，将可见性设置为 `hidden` 会导致工具栏即使在全屏模式下也保持完全隐藏。


---
source: https://developer.apple.com/documentation/SwiftUI/WindowToolbarFullScreenVisibility/visible
crawled: 2025-12-03T05:32:30Z
---

# visible

**Type Property**

Prefer to show window toolbar when the window is in full screen mode.

## Declaration

```swift
static let visible: WindowToolbarFullScreenVisibility
```

## Discussion

This has no effect if the toolbar is completely hidden, i.e. setting the visibility to `hidden` for `windowToolbar` placements using [toolbarVisibility(_:for:)](../View/toolbarVisibility___for.zh-Hans.md) will cause the toolbar to remain completely hidden, even in full screen.

