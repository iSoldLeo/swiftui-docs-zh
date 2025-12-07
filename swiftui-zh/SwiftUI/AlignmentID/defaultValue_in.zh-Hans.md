--- 来源：https://developer.apple.com/documentation/SwiftUI/AlignmentID/defaultValue(in:)

抓取时间：2025-12-01T11:26:15Z

---

# defaultValue(in:)

**类型方法**

计算指定上下文中对应参考线的默认值。

## 声明

```swift
static func defaultValue(in context: ViewDimensions) -> CGFloat
```

## 参数

- **context**：应用对齐参考线的视图的上下文。上下文包含视图的尺寸，以及应用于该视图的其他对齐参考线的值，包括内置参考线和自定义参考线。如果需要，您可以使用这些值来计算自定义参考线的值。

## 返回值

参考线在视图坐标空间中相对于原点的偏移量。

## 讨论

创建符合 [AlignmentID](../AlignmentID.zh-Hans.md) 协议的类型时，请实现此方法。使用此方法计算相应对齐参考线的默认偏移量。SwiftUI 会将返回值解释为正在布局的视图坐标空间中的偏移量。例如，您可以使用上下文返回视图高度的三分之一：

```swift
private struct FirstThirdAlignment: AlignmentID {
    static func defaultValue(in context: ViewDimensions) -> CGFloat {
        context.height / 3
    }
}
```

您可以通过向特定视图添加 [alignmentGuide(_:computeValue:)](../View/alignmentGuide___computeValue.zh-Hans.md) 视图修饰符来覆盖此方法为特定参考线返回的默认值。


---
source: https://developer.apple.com/documentation/SwiftUI/AlignmentID/defaultValue(in:)
crawled: 2025-12-01T11:26:15Z
---

# defaultValue(in:)

**Type Method**

Calculates a default value for the corresponding guide in the specified context.

## Declaration

```swift
static func defaultValue(in context: ViewDimensions) -> CGFloat
```

## Parameters

- **context**: The context of the view that you apply the alignment guide to. The context gives you the view’s dimensions, as well as the values of other alignment guides that apply to the view, including both built-in and custom guides. You can use any of these values, if helpful, to calculate the value for your custom guide.

## Return Value

The offset of the guide from the origin in the view’s coordinate space.

## Discussion

Implement this method when you create a type that conforms to the [AlignmentID](../AlignmentID.zh-Hans.md) protocol. Use the method to calculate the default offset of the corresponding alignment guide. SwiftUI interprets the value that you return as an offset in the coordinate space of the view that’s being laid out. For example, you can use the context to return a value that’s one-third of the height of the view:

```swift
private struct FirstThirdAlignment: AlignmentID {
    static func defaultValue(in context: ViewDimensions) -> CGFloat {
        context.height / 3
    }
}
```

You can override the default value that this method returns for a particular guide by adding the [alignmentGuide(_:computeValue:)](../View/alignmentGuide___computeValue.zh-Hans.md) view modifier to a particular view.

