---
来源： https://developer.apple.com/documentation/SwiftUI/WorldScalingBehavior/dynamic
抓取时间： 2025-12-02T16:21:21Z
---

# 动态

**类型属性**

窗口会随着移动距离的增加而缩放，但角度大小保持不变。

## 声明

```swift
static var dynamic: WorldScalingBehavior { get }
```

## 讨论

对于显示密集用户界面或大量文本的窗口，建议使用动态窗口缩放。使用动态缩放可确保控件和文本保持舒适的大小，而不受窗口位置的影响。

有关详细信息，请参阅《人机界面指南》中的[doc://com.apple.documentation/design/Human-Interface-Guidelines/spatial-layout#Scale]。


---
source: https://developer.apple.com/documentation/SwiftUI/WorldScalingBehavior/dynamic
crawled: 2025-12-02T16:21:21Z
---

# dynamic

**Type Property**

The window will scale up as it moves further away, maintaining the same angular size.

## Declaration

```swift
static var dynamic: WorldScalingBehavior { get }
```

## Discussion

Prefer dynamic window scaling for windows that display dense UI or a lot of text. Using dynamic scaling ensures that controls and text remain at a comfortable size regardless of the window’s position.

For further information, see [doc://com.apple.documentation/design/Human-Interface-Guidelines/spatial-layout#Scale] in the Human Interface Guidelines.

