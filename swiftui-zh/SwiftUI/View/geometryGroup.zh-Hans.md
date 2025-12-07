---

来源：https://developer.apple.com/documentation/SwiftUI/View/geometryGroup()

抓取时间：2025-11-30T21:19:25Z

---

# geometryGroup()

**实例方法**

将子视图的几何体（例如位置和大小）与其父视图隔离。

## 声明

```swift
nonisolated func geometryGroup() -> some View

```

## 讨论

默认情况下，SwiftUI 视图会将位置和大小的更改向下传递到视图层级结构中，因此只有绘制内容的视图（称为叶视图）才会将当前动画应用于其框架矩形。然而，在某些情况下，这种合并行为可能会导致不理想的结果；插入几何组可以纠正这种情况。几何组充当父视图及其子视图之间的屏障，强制父视图解析和动画化位置和大小值，然后再将其传递给每个子视图。

以下示例展示了此函数的一种用法：确保堆栈中每一行的成员视图应用（并以动画形式呈现）来自其父视图的单一几何变换，而不是让父视图的效果分别应用于每个叶视图。如果 `ItemView` 的成员可能在不同时间被添加和移除，则该组可确保它们在应用动画时保持锁定状态。

```swift
VStack {
    ForEach(items) { item in
        ItemView(item: item)
            .geometryGroup()
    }
}
```

返回：一个几何体与其父视图的几何体隔离的新视图。

## 同步几何体

- **matchedGeometryEffect(id:in:properties:anchor:isSource:)**：使用您提供的标识符和命名空间定义一组具有同步几何体的视图。

- **MatchedGeometryProperties**：一组视图属性，可以使用 `View.matchedGeometryEffect()` 函数在视图之间同步这些属性。

- **GeometryEffect**：一种改变视图视觉外观的效果，但基本不会改变其父视图或子视图。

- **Namespace**：一种动态属性类型，允许访问由包含该属性的对象（例如视图）的持久标识定义的命名空间。


---
source: https://developer.apple.com/documentation/SwiftUI/View/geometryGroup()
crawled: 2025-11-30T21:19:25Z
---

# geometryGroup()

**Instance Method**

Isolates the geometry (e.g. position and size) of the view from its parent view.

## Declaration

```swift
nonisolated func geometryGroup() -> some View

```

## Discussion

By default SwiftUI views push position and size changes down through the view hierarchy, so that only views that draw something (known as leaf views) apply the current animation to their frame rectangle. However in some cases this coalescing behavior can give undesirable results; inserting a geometry group can correct that. A group acts as a barrier between the parent view and its subviews, forcing the position and size values to be resolved and animated by the parent, before being passed down to each subview.

The example below shows one use of this function: ensuring that the member views of each row in the stack apply (and animate as) a single geometric transform from their ancestor view, rather than letting the effects of the ancestor views be applied separately to each leaf view. If the members of `ItemView` may be added and removed at different times the group ensures that they stay locked together as animations are applied.

```swift
VStack {
    ForEach(items) { item in
        ItemView(item: item)
            .geometryGroup()
    }
}
```

Returns: a new view whose geometry is isolated from that of its parent view.

## Synchronizing geometries

- **matchedGeometryEffect(id:in:properties:anchor:isSource:)**: Defines a group of views with synchronized geometry using an identifier and namespace that you provide.
- **MatchedGeometryProperties**: A set of view properties that may be synchronized between views using the `View.matchedGeometryEffect()` function.
- **GeometryEffect**: An effect that changes the visual appearance of a view, largely without changing its ancestors or descendants.
- **Namespace**: A dynamic property type that allows access to a namespace defined by the persistent identity of the object containing the property (e.g. a view).

