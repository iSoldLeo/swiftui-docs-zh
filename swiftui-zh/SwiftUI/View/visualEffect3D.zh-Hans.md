--- 来源：https://developer.apple.com/documentation/SwiftUI/View/visualEffect3D(_:)

抓取时间：2025-12-02T17:37:27Z

---

# visualEffect3D(_:)

**实例方法**

将效果应用于此视图，并通过 3D 几何代理提供对布局信息的访问。

## 声明

```swift
nonisolated func visualEffect3D(_ effect: @escaping (EmptyVisualEffect, GeometryProxy3D) -> some VisualEffect) -> some View

```

## 参数

- **effect**：返回要应用的效果的闭包。传递给闭包的第一个参数是表示此视图的占位符。第二个参数是 `GeometryProxy3D`。

## 返回值

应用了效果的视图。

## 讨论

您可以通过调用传递给 `effect` 闭包的第一个参数上的函数来返回新的效果。在本例中，`ContentView` 沿 Z 轴偏移其自身深度，使其背面出现在视图正面原本所在的位置：

```swift
ContentView()
    .visualEffect3D { content, geometryProxy in
        content.offset(z: geometryProxy.size.depth)
    }
```

## 基于几何体应用效果

- **visualEffect(_:)**：将效果应用于此视图，同时通过几何体代理提供对布局信息的访问。

- **VisualEffect**：视觉效果会改变视图的视觉外观，而不会改变其祖先或后代。

- **EmptyVisualEffect**：您应用其他效果的基础视觉效果。


---
source: https://developer.apple.com/documentation/SwiftUI/View/visualEffect3D(_:)
crawled: 2025-12-02T17:37:27Z
---

# visualEffect3D(_:)

**Instance Method**

Applies effects to this view, while providing access to layout information through a 3D geometry proxy.

## Declaration

```swift
nonisolated func visualEffect3D(_ effect: @escaping (EmptyVisualEffect, GeometryProxy3D) -> some VisualEffect) -> some View

```

## Parameters

- **effect**: A closure that returns the effect to be applied. The first argument provided to the closure is a placeholder representing this view. The second argument is a `GeometryProxy3D`.

## Return Value

A view with the effect applied.

## Discussion

You return new effects by calling functions on the first argument provided to the `effect` closure. In this example, `ContentView` is offset in Z by its own depth, causing its back face to appear where the front face of the view was originally located:

```swift
ContentView()
    .visualEffect3D { content, geometryProxy in
        content.offset(z: geometryProxy.size.depth)
    }
```

## Applying effects based on geometry

- **visualEffect(_:)**: Applies effects to this view, while providing access to layout information through a geometry proxy.
- **VisualEffect**: Visual Effects change the visual appearance of a view without changing its ancestors or descendents.
- **EmptyVisualEffect**: The base visual effect that you apply additional effect to.

