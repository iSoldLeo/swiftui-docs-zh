---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/labelReservedIconWidth
抓取时间： 2025-12-03T06:08:10Z
---

# labelReservedIconWidth

**实例属性**

为标签中的图标预留的宽度。

## 声明

```swift
var labelReservedIconWidth: CGFloat? { get }
```

## 讨论

标签中预留图标宽度的值。要为标签设置不同的值，请使用 `labelReservedIconWidth` 修改器。

该环境值可用于自定义标签样式，以便使用 `labelReservedIconWidth` 修改器更改预留图标宽度。如果该值为`nil`，则应使用默认行为来调整图标大小。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/labelReservedIconWidth
crawled: 2025-12-03T06:08:10Z
---

# labelReservedIconWidth

**Instance Property**

The width reserved for icons in labels.

## Declaration

```swift
var labelReservedIconWidth: CGFloat? { get }
```

## Discussion

The value that should be used for the reserved icon width in labels. To set a different value for labels, use the `labelReservedIconWidth` modifier.

This environment value can be used in custom label styles to allow changing the reserved icon width using the `labelReservedIconWidth` modifier. If the value is `nil`, a default behavior to size the icon should be used instead.

