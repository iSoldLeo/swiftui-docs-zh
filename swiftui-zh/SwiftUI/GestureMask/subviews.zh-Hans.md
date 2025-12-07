---
来源：https://developer.apple.com/documentation/SwiftUI/GestureMask/subviews
抓取时间： 2025-12-03T06:43:38Z
---

# 子视图

**类型属性**

启用子视图层级中的所有手势，但禁用添加的手势。

## 声明

```swift
static let subviews: GestureMask
```

## 获取手势选项

- **all**：在视图及其子视图上启用添加的手势和所有其他手势。
- **gesture**：启用添加的手势，但禁用子视图层次结构中的所有手势。
- **none**：禁用子视图层次结构中的所有手势，包括添加的手势。


---
source: https://developer.apple.com/documentation/SwiftUI/GestureMask/subviews
crawled: 2025-12-03T06:43:38Z
---

# subviews

**Type Property**

Enable all gestures in the subview hierarchy but disable the added gesture.

## Declaration

```swift
static let subviews: GestureMask
```

## Getting gesture options

- **all**: Enable both the added gesture as well as all other gestures on the view and its subviews.
- **gesture**: Enable the added gesture but disable all gestures in the subview hierarchy.
- **none**: Disable all gestures in the subview hierarchy, including the added gesture.

