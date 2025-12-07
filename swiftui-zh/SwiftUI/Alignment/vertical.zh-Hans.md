--- 来源：https://developer.apple.com/documentation/SwiftUI/Alignment/vertical
抓取时间：2025-12-03T06:36:37Z

---

# vertical

**实例属性**

垂直轴的对齐方式。

## 声明

```swift
var vertical: VerticalAlignment
```

## 说明

使用 [init(horizontal:vertical:)](init_horizontal_vertical.zh-Hans.md) 方法初始化对齐方式时，请设置此值。可以使用内置的 [VerticalAlignment](../VerticalAlignment.zh-Hans.md) 参考线（例如 [center](../VerticalAlignment/center.zh-Hans.md)），也可以使用您创建的自定义参考线。

有关创建自定义参考线的信息，请参阅 [AlignmentID](../AlignmentID.zh-Hans.md)。

## 创建自定义对齐方式

- **init(horizontal:vertical:)**：使用指定的水平和垂直对齐参考线创建自定义对齐值。

- **horizontal**：水平轴对齐方式。


---
source: https://developer.apple.com/documentation/SwiftUI/Alignment/vertical
crawled: 2025-12-03T06:36:37Z
---

# vertical

**Instance Property**

The alignment on the vertical axis.

## Declaration

```swift
var vertical: VerticalAlignment
```

## Discussion

Set this value when you initialize an alignment using the [init(horizontal:vertical:)](init_horizontal_vertical.zh-Hans.md) method. Use one of the built-in [VerticalAlignment](../VerticalAlignment.zh-Hans.md) guides, like [center](../VerticalAlignment/center.zh-Hans.md), or a custom guide that you create.

For information about creating custom guides, see [AlignmentID](../AlignmentID.zh-Hans.md).

## Creating a custom alignment

- **init(horizontal:vertical:)**: Creates a custom alignment value with the specified horizontal and vertical alignment guides.
- **horizontal**: The alignment on the horizontal axis.

