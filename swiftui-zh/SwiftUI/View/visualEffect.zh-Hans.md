--- 来源：https://developer.apple.com/documentation/SwiftUI/View/visualEffect(_:)

抓取时间：2025-11-30T21:22:32Z

---

# visualEffect(_:)

**实例方法**

将效果应用于此视图，同时通过几何代理提供对布局信息的访问。

## 声明

```swift
nonisolated func visualEffect(_ effect: @escaping (EmptyVisualEffect, GeometryProxy) -> some VisualEffect) -> some View

```

## 参数

- **effect**：返回要应用的效果的闭包。传递给闭包的第一个参数是表示此视图的占位符。第二个参数是 `GeometryProxy`。

## 返回值

应用了效果的视图。

## 说明

您可以通过调用传递给 `effect` 闭包的第一个参数上的函数来返回新的效果。在本例中，`ContentView` 会根据自身大小进行偏移，导致其左上角出现在原本右下角所在的位置：

```swift
ContentView()
    .visualEffect { content, geometryProxy in
        content.offset(geometryProxy.size)
    }
```

## 应用基于几何体的效果

- **visualEffect3D(_:)**：对当前视图应用效果，同时通过 3D 几何体代理提供对布局信息的访问。

- **VisualEffect**：视觉效果会改变视图的视觉外观，而不会改变其父视图或子视图。

- **EmptyVisualEffect**：基础视觉效果，在此基础上应用其他效果。


---
source: https://developer.apple.com/documentation/SwiftUI/View/visualEffect(_:)
crawled: 2025-11-30T21:22:32Z
---

# visualEffect(_:)

**Instance Method**

Applies effects to this view, while providing access to layout information through a geometry proxy.

## Declaration

```swift
nonisolated func visualEffect(_ effect: @escaping (EmptyVisualEffect, GeometryProxy) -> some VisualEffect) -> some View

```

## Parameters

- **effect**: A closure that returns the effect to be applied. The first argument provided to the closure is a placeholder representing this view. The second argument is a `GeometryProxy`.

## Return Value

A view with the effect applied.

## Discussion

You return new effects by calling functions on the first argument provided to the `effect` closure. In this example, `ContentView` is offset by its own size, causing its top left corner to appear where the bottom right corner was originally located:

```swift
ContentView()
    .visualEffect { content, geometryProxy in
        content.offset(geometryProxy.size)
    }
```

## Applying effects based on geometry

- **visualEffect3D(_:)**: Applies effects to this view, while providing access to layout information through a 3D geometry proxy.
- **VisualEffect**: Visual Effects change the visual appearance of a view without changing its ancestors or descendents.
- **EmptyVisualEffect**: The base visual effect that you apply additional effect to.

