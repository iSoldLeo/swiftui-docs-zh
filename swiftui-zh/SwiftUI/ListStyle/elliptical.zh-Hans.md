---
来源： https://developer.apple.com/documentation/SwiftUI/ListStyle/elliptical
抓取时间： 2025-12-03T06:10:49Z
---

# 椭圆

**类型属性**

描述椭圆列表行为和外观的列表样式。

## 声明

```swift
static var elliptical: EllipticalListStyle { get }
```

## 讨论

在 watchOS 上，椭圆列表样式会对从列表顶部或底部滚动的项目进行变换，就像在面向用户的圆形表面上一样。

Apple Watch Series 3 不支持这种样式，而是转回使用[plain](plain.zh-Hans.md)样式。

## 获取内置列表样式

- **automatic**：描述平台默认行为和列表外观的列表样式。
- **bordered**：列表样式，用于描述带有标准边框的列表的行为和外观。
- **carousel**：旋转木马列表样式。
- **grouped**：旋转木马列表样式：描述分组列表的行为和外观的列表样式。
- **inset**：描述插入列表的行为和外观的列表样式。
- **insetGrouped**：描述插入分组列表的行为和外观的列表样式。
- **plain**：描述普通列表的行为和外观的列表样式。
- **sidebar**：描述侧边栏列表行为和外观的列表样式。


---
source: https://developer.apple.com/documentation/SwiftUI/ListStyle/elliptical
crawled: 2025-12-03T06:10:49Z
---

# elliptical

**Type Property**

The list style that describes the behavior and appearance of an elliptical list.

## Declaration

```swift
static var elliptical: EllipticalListStyle { get }
```

## Discussion

On watchOS, the elliptical list style uses a transform for items rolling off the top or bottom of the list, as if on a rounded surface that faces the user.

Apple Watch Series 3 does not support this style and will instead fall back to using the [plain](plain.zh-Hans.md) style.

## Getting built-in list styles

- **automatic**: The list style that describes a platform’s default behavior and appearance for a list.
- **bordered**: The list style that describes the behavior and appearance of a list with standard border.
- **carousel**: The carousel list style.
- **grouped**: The list style that describes the behavior and appearance of a grouped list.
- **inset**: The list style that describes the behavior and appearance of an inset list.
- **insetGrouped**: The list style that describes the behavior and appearance of an inset grouped list.
- **plain**: The list style that describes the behavior and appearance of a plain list.
- **sidebar**: The list style that describes the behavior and appearance of a sidebar list.

