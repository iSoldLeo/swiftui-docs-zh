---
来源： https://developer.apple.com/documentation/SwiftUI/GestureMask/none
抓取时间： 2025-12-03T06:43:38Z
---

# 无

**类型属性**

禁用子视图层级中的所有手势，包括添加的手势。

## 声明

```swift
static let none: GestureMask
```

## 获取手势选项

- **all**：在视图及其子视图上启用添加的手势和所有其他手势。
- **gesture**：启用添加的手势，但禁用子视图层次结构中的所有手势。
- **subviews**：启用子视图层次结构中的所有手势，但禁用添加的手势。


---
source: https://developer.apple.com/documentation/SwiftUI/GestureMask/none
crawled: 2025-12-03T06:43:38Z
---

# none

**Type Property**

Disable all gestures in the subview hierarchy, including the added gesture.

## Declaration

```swift
static let none: GestureMask
```

## Getting gesture options

- **all**: Enable both the added gesture as well as all other gestures on the view and its subviews.
- **gesture**: Enable the added gesture but disable all gestures in the subview hierarchy.
- **subviews**: Enable all gestures in the subview hierarchy but disable the added gesture.

