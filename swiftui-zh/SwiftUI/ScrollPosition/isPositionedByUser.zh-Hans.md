--- 来源：https://developer.apple.com/documentation/SwiftUI/ScrollPosition/isPositionedByUser
抓取时间：2025-12-03T06:42:00Z

---

# isPositionedByUser

**实例属性**

滚动视图是否由用户定位。

## 声明

```swift
var isPositionedByUser: Bool { get set }
```

## 说明

您可以写入此属性来控制滚动视图是否表现得像由用户定位一样。如果位置值不为空，则将此属性设置为 true 时，该值将变为 nil。


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollPosition/isPositionedByUser
crawled: 2025-12-03T06:42:00Z
---

# isPositionedByUser

**Instance Property**

Whether the scroll view has been positioned by the user.

## Declaration

```swift
var isPositionedByUser: Bool { get set }
```

## Discussion

You can write to this property to control whether the scroll view acts as if it has been positioned by the user. If the position had a non-nil edge / point value, that value will become nil when setting this property to true.

