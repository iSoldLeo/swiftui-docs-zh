--- 来源：https://developer.apple.com/documentation/SwiftUI/DisplayProxy/visibleRect

抓取时间：2025-12-03T05:32:24Z

---

# visibleRect

**实例属性**

屏幕上可以安全放置窗口的区域。

## 声明

```swift
let visibleRect: CGRect
```

## 讨论

在 macOS 系统中，此区域不包含 Dock 栏和菜单栏所占据的空间。此外，对于边框内包含摄像头外壳的 Mac 电脑，此矩形区域也不包含边框或边框两侧的可见区域。


---
source: https://developer.apple.com/documentation/SwiftUI/DisplayProxy/visibleRect
crawled: 2025-12-03T05:32:24Z
---

# visibleRect

**Instance Property**

The portion of the display where it is safe to place windows.

## Declaration

```swift
let visibleRect: CGRect
```

## Discussion

On macOS, this area does not contain the space occupied by the dock and menu bar. Additionally, on Macs that include a camera housing in the bezel this rectangle does not include the bezel or visible areas to each side of the bezel.

