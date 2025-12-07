--- 来源：https://developer.apple.com/documentation/SwiftUI/WindowPlacement/Position/replacing(_:)

抓取时间：2025-12-02T15:01:12Z

---

# replacement(_:)

**类型方法**

将新窗口放置在与现有窗口相同的位置，同时隐藏旧窗口。

## 声明

```swift
static func replacing(_ relativeWindow: WindowProxy) -> WindowPlacement.Position
```

## 参数

- **relativeWindow**：新窗口将替换的现有窗口。

## 说明

此方法会将新窗口放置在与指定现有窗口相同的位置，并隐藏旧窗口。关闭新窗口后，原窗口将再次显示。


---
source: https://developer.apple.com/documentation/SwiftUI/WindowPlacement/Position/replacing(_:)
crawled: 2025-12-02T15:01:12Z
---

# replacing(_:)

**Type Method**

Positions the window in the same spot as an existing window, hiding the old window in the process.

## Declaration

```swift
static func replacing(_ relativeWindow: WindowProxy) -> WindowPlacement.Position
```

## Parameters

- **relativeWindow**: The existing window that the new window will replace.

## Discussion

This will position the new window in the same location as the specified existing window, and hide the old window. Closing the new window will then result in the original window being shown again.

