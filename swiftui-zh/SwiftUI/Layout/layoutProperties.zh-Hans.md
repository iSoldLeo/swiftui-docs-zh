---
来源： https://developer.apple.com/documentation/SwiftUI/Layout/layoutProperties
抓取时间： 2025-12-02T17:53:09Z
---

# 布局属性

**类型属性**

布局容器的属性。

## 声明

```swift
static var layoutProperties: LayoutProperties { get }
```

## 讨论

在符合[Layout](../Layout.zh-Hans.md) 协议的类型中实现此属性，以描述自定义布局容器的特征。例如，您可以表示您的布局具有垂直[stackOrientation](../LayoutProperties/stackOrientation.zh-Hans.md)：

```swift
extension BasicVStack {
    static var layoutProperties: LayoutProperties {
        var properties = LayoutProperties()
        properties.stackOrientation = .vertical
        return properties
    }
}
```

如果您没有在自定义布局中实现该属性，协议会提供一个默认实现，即[doc://com.apple.SwiftUI/documentation/SwiftUI/Layout/layoutProperties-6h7w0]，它会返回一个具有默认值的[LayoutProperties](../LayoutProperties.zh-Hans.md)实例。

## 报告布局容器特征

- **explicitAlignment(of:in:proposal:subviews:cache:)**：返回指定的水平对齐向导沿 x 轴的位置。
- **spacing(subviews:cache:)**：返回合成视图的首选间距值。


---
source: https://developer.apple.com/documentation/SwiftUI/Layout/layoutProperties
crawled: 2025-12-02T17:53:09Z
---

# layoutProperties

**Type Property**

Properties of a layout container.

## Declaration

```swift
static var layoutProperties: LayoutProperties { get }
```

## Discussion

Implement this property in a type that conforms to the [Layout](../Layout.zh-Hans.md) protocol to characterize your custom layout container. For example, you can indicate that your layout has a vertical [stackOrientation](../LayoutProperties/stackOrientation.zh-Hans.md):

```swift
extension BasicVStack {
    static var layoutProperties: LayoutProperties {
        var properties = LayoutProperties()
        properties.stackOrientation = .vertical
        return properties
    }
}
```

If you don’t implement this property in your custom layout, the protocol provides a default implementation, namely [doc://com.apple.SwiftUI/documentation/SwiftUI/Layout/layoutProperties-6h7w0], that returns a [LayoutProperties](../LayoutProperties.zh-Hans.md) instance with default values.

## Reporting layout container characteristics

- **explicitAlignment(of:in:proposal:subviews:cache:)**: Returns the position of the specified horizontal alignment guide along the x axis.
- **spacing(subviews:cache:)**: Returns the preferred spacing values of the composite view.

