--- 来源：https://developer.apple.com/documentation/SwiftUI/ShapeStyle/body
抓取时间：2025-12-03T06:25:30Z

---

# body

**实例属性**

一个填充了形状样式的矩形视图。

## 声明

```swift
var body: _ShapeView<Rectangle, Self> { get }
```

## 讨论

对于也符合 [View](../View.zh-Hans.md) 协议的 [ShapeStyle](../ShapeStyle.zh-Hans.md) 视图（例如 [Color](../Color.zh-Hans.md) 或 [LinearGradient](../LinearGradient.zh-Hans.md)），此 [body-8kl5o](../View/body-8kl5o.zh-Hans.md) 属性的默认实现提供了形状样式的可视化表示。因此，您可以像使用任何其他视图一样，在视图层次结构中使用此形状样式：

```swift
ZStack {
    Color.cyan
    Text("Hello!")
}
.frame(width: 200, height: 50)
```


---
source: https://developer.apple.com/documentation/SwiftUI/ShapeStyle/body
crawled: 2025-12-03T06:25:30Z
---

# body

**Instance Property**

A rectangular view that’s filled with the shape style.

## Declaration

```swift
var body: _ShapeView<Rectangle, Self> { get }
```

## Discussion

For a [ShapeStyle](../ShapeStyle.zh-Hans.md) that also conforms to the [View](../View.zh-Hans.md) protocol, like [Color](../Color.zh-Hans.md) or [LinearGradient](../LinearGradient.zh-Hans.md), this default implementation of the [body-8kl5o](../View/body-8kl5o.zh-Hans.md) property provides a visual representation for the shape style. As a result, you can use the shape style in a view hierarchy like any other view:

```swift
ZStack {
    Color.cyan
    Text("Hello!")
}
.frame(width: 200, height: 50)
```



