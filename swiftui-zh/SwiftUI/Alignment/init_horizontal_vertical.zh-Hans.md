--- 来源：https://developer.apple.com/documentation/SwiftUI/Alignment/init(horizontal:vertical:)

抓取时间：2025-12-01T11:25:47Z

---

# init(horizontal:vertical:)

**Initializer**

使用指定的水平和垂直对齐参考线创建自定义对齐值。

## 声明

```swift
init(horizontal: HorizontalAlignment, vertical: VerticalAlignment)
```

## 参数

- **horizontal**：水平轴对齐方式。

- **vertical**：垂直轴对齐方式。

## 讨论

SwiftUI 提供了多种内置对齐方式，这些方式结合了内置的 [HorizontalAlignment](../HorizontalAlignment.zh-Hans.md) 和 [VerticalAlignment](../VerticalAlignment.zh-Hans.md) 参考线。使用此初始化程序创建自定义对齐方式，该对齐方式可使用自定义水平或垂直参考线，或两者都使用。

例如，您可以将名为 `firstThird` 的自定义垂直参考线与内置参考线 [center](../HorizontalAlignment/center.zh-Hans.md) 结合使用，并使用它来配置 [ZStack](../ZStack.zh-Hans.md)：

```swift
ZStack(alignment: Alignment(horizontal: .center, vertical: .firstThird)) {
    // ...
}
```

有关创建自定义参考线的更多信息，包括上述示例中创建自定义对齐方式 `firstThird` 的代码，请参阅 [AlignmentID](../AlignmentID.zh-Hans.md)。

## 创建自定义对齐方式

- **horizontal**：水平轴上的对齐方式。

- **vertical**：垂直轴上的对齐方式。


---
source: https://developer.apple.com/documentation/SwiftUI/Alignment/init(horizontal:vertical:)
crawled: 2025-12-01T11:25:47Z
---

# init(horizontal:vertical:)

**Initializer**

Creates a custom alignment value with the specified horizontal and vertical alignment guides.

## Declaration

```swift
init(horizontal: HorizontalAlignment, vertical: VerticalAlignment)
```

## Parameters

- **horizontal**: The alignment on the horizontal axis.
- **vertical**: The alignment on the vertical axis.

## Discussion

SwiftUI provides a variety of built-in alignments that combine built-in [HorizontalAlignment](../HorizontalAlignment.zh-Hans.md) and [VerticalAlignment](../VerticalAlignment.zh-Hans.md) guides. Use this initializer to create a custom alignment that makes use of a custom horizontal or vertical guide, or both.

For example, you can combine a custom vertical guide called `firstThird` with the built-in [center](../HorizontalAlignment/center.zh-Hans.md) guide, and use it to configure a [ZStack](../ZStack.zh-Hans.md):

```swift
ZStack(alignment: Alignment(horizontal: .center, vertical: .firstThird)) {
    // ...
}
```

For more information about creating custom guides, including the code that creates the custom `firstThird` alignment in the example above, see [AlignmentID](../AlignmentID.zh-Hans.md).

## Creating a custom alignment

- **horizontal**: The alignment on the horizontal axis.
- **vertical**: The alignment on the vertical axis.

