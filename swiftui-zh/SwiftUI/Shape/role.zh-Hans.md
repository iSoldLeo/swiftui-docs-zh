---
来源： https://developer.apple.com/documentation/SwiftUI/Shape/role
抓取时间： 2025-12-02T21:41:59Z
---

# 角色

**类型属性**

形状样式的指示。

## 声明

```swift
nonisolated static var role: ShapeRole { get }
```

## 讨论

SwiftUI 在决定如何在渲染时应用[ShapeStyle](../ShapeStyle.zh-Hans.md) 时会查看形状的角色。[Shape](../Shape.zh-Hans.md)协议提供了一个值为[fill](../ShapeRole/fill.zh-Hans.md)的默认实现。如果您创建了一个复合形状，您可以提供对该属性的覆盖，以返回另一个合适的值。


---
source: https://developer.apple.com/documentation/SwiftUI/Shape/role
crawled: 2025-12-02T21:41:59Z
---

# role

**Type Property**

An indication of how to style a shape.

## Declaration

```swift
nonisolated static var role: ShapeRole { get }
```

## Discussion

SwiftUI looks at a shape’s role when deciding how to apply a [ShapeStyle](../ShapeStyle.zh-Hans.md) at render time. The [Shape](../Shape.zh-Hans.md) protocol provides a default implementation with a value of [fill](../ShapeRole/fill.zh-Hans.md). If you create a composite shape, you can provide an override of this property to return another value, if appropriate.

