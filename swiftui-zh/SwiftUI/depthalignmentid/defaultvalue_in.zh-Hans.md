---
来源： https://developer.apple.com/documentation/swiftui/depthalignmentid/defaultvalue(in:)
抓取时间： 2025-12-03T06:35:40Z
---

# defaultValue(in:)

**类型方法**

计算指定上下文中相应向导的默认值。

## 声明

```swift
static func defaultValue(in context: ViewDimensions3D) -> CGFloat
```

## 参数

- **context**：应用排列向导的视图的上下文。上下文提供了视图的尺寸，以及适用于该视图的其他对齐方式的值，包括内置和自定义对齐方式。如果有用，您可以使用这些值中的任何一个来计算自定义向导的值。

## 返回值

在视图的坐标空间中，从原点到导轨的偏移量。

## 讨论

创建符合[DepthAlignmentID](../DepthAlignmentID.zh-Hans.md) 协议的类型时，请执行本方法。使用该方法计算相应对齐指南的默认偏移量。SwiftUI 将返回的值解释为正在布局的视图坐标空间中的偏移量。例如，您可以使用上下文返回视图高度三分之一的值：

```swift
private struct FirstThirdAlignment: DepthAlignmentID {
    static func defaultValue(in context: ViewDimensions3D) -> CGFloat {
        context.depth / 3
    }
}
```

通过向特定视图添加[alignmentGuide(_:computeValue:)](../View/alignmentGuide___computeValue.zh-Hans.md) 视图修饰符，可以覆盖此方法为特定向导返回的默认值。


---
source: https://developer.apple.com/documentation/swiftui/depthalignmentid/defaultvalue(in:)
crawled: 2025-12-03T06:35:40Z
---

# defaultValue(in:)

**Type Method**

Calculates a default value for the corresponding guide in the specified context.

## Declaration

```swift
static func defaultValue(in context: ViewDimensions3D) -> CGFloat
```

## Parameters

- **context**: The context of the view that you apply the alignment guide to. The context gives you the view’s dimensions, as well as the values of other alignment guides that apply to the view, including both built-in and custom guides. You can use any of these values, if helpful, to calculate the value for your custom guide.

## Return Value

The offset of the guide from the origin in the view’s coordinate space.

## Discussion

Implement this method when you create a type that conforms to the [DepthAlignmentID](../DepthAlignmentID.zh-Hans.md) protocol. Use the method to calculate the default offset of the corresponding alignment guide. SwiftUI interprets the value that you return as an offset in the coordinate space of the view that’s being laid out. For example, you can use the context to return a value that’s one-third of the height of the view:

```swift
private struct FirstThirdAlignment: DepthAlignmentID {
    static func defaultValue(in context: ViewDimensions3D) -> CGFloat {
        context.depth / 3
    }
}
```

You can override the default value that this method returns for a particular guide by adding the [alignmentGuide(_:computeValue:)](../View/alignmentGuide___computeValue.zh-Hans.md) view modifier to a particular view.

