--- 来源：https://developer.apple.com/documentation/SwiftUI/View/matchedGeometryEffect(id:in:properties:anchor:isSource:)

抓取时间：2025-11-30T21:19:21Z

---

# matchedGeometryEffect(id:in:properties:anchor:isSource:)

**实例方法**

使用您提供的标识符和命名空间，定义一组具有同步几何图形的视图。

## 声明

```swift
nonisolated func matchedGeometryEffect<ID>(id: ID, in namespace: Namespace.ID, properties: MatchedGeometryProperties = .frame, anchor: UnitPoint = .center, isSource: Bool = true) -> some View where ID : Hashable

```

## 参数

- **id**：标识符，通常派生自视图所显示数据的标识符。

- **namespace**：定义 `id` 的命名空间。通过将 `@Namespace` 变量添加到 [View](../View.zh-Hans.md) 类型，并在视图的 body 方法中读取其值，即可创建新的命名空间。

- **properties**：要从源视图复制的属性。

- **anchor**：用于生成共享位置值的视图中的相对位置。

- **isSource**：如果该视图应用作组中其他视图的几何体源，则返回 True。

## 返回值

一个新视图，该视图在全局视图数据库中定义了一个条目，用于同步它们的几何体。

## 说明

此方法使用 `isSource = true` 插入的视图（称为“源”视图）设置组中每个视图的几何体，并更新由 `properties` 标记的值。

如果在同一事务中插入一个视图的同时，又移除了另一个具有相同键的视图，系统会在窗口空间中插值它们的框架矩形，使之看起来像是一个视图从旧位置移动到了新位置。通常的过渡机制定义了过渡期间两个视图的渲染方式（例如淡入/淡出、缩放等），而 `matchedGeometryEffect()` 修饰符仅用于链接视图的几何体，而不涉及它们的渲染方式。

如果 `isSource = true` 修饰符组中当前插入的视图数量不为 1，则结果未定义，因为无法确定哪个视图是源视图。

## 同步几何体

- **MatchedGeometryProperties**：一组视图属性，可以使用 `View.matchedGeometryEffect()` 函数在视图之间同步这些属性。

- **GeometryEffect**：一种改变视图视觉外观的效果，基本不会改变其父视图或子视图。

- **Namespace**：一种动态属性类型，允许访问由包含该属性的对象（例如视图）的持久标识定义的命名空间。

- **geometryGroup()**：将视图的几何体（例如位置和大小）与其父视图隔离。


---
source: https://developer.apple.com/documentation/SwiftUI/View/matchedGeometryEffect(id:in:properties:anchor:isSource:)
crawled: 2025-11-30T21:19:21Z
---

# matchedGeometryEffect(id:in:properties:anchor:isSource:)

**Instance Method**

Defines a group of views with synchronized geometry using an identifier and namespace that you provide.

## Declaration

```swift
nonisolated func matchedGeometryEffect<ID>(id: ID, in namespace: Namespace.ID, properties: MatchedGeometryProperties = .frame, anchor: UnitPoint = .center, isSource: Bool = true) -> some View where ID : Hashable

```

## Parameters

- **id**: The identifier, often derived from the identifier of the data being displayed by the view.
- **namespace**: The namespace in which defines the `id`. New namespaces are created by adding an `@Namespace` variable to a [View](../View.zh-Hans.md) type and reading its value in the view’s body method.
- **properties**: The properties to copy from the source view.
- **anchor**: The relative location in the view used to produce its shared position value.
- **isSource**: True if the view should be used as the source of geometry for other views in the group.

## Return Value

A new view that defines an entry in the global database of views synchronizing their geometry.

## Discussion

This method sets the geometry of each view in the group from the inserted view with `isSource = true` (known as the “source” view), updating the values marked by `properties`.

If inserting a view in the same transaction that another view with the same key is removed, the system will interpolate their frame rectangles in window space to make it appear that there is a single view moving from its old position to its new position. The usual transition mechanisms define how each of the two views is rendered during the transition (e.g. fade in/out, scale, etc), the `matchedGeometryEffect()` modifier only arranges for the geometry of the views to be linked, not their rendering.

If the number of currently-inserted views in the group with `isSource = true` is not exactly one results are undefined, due to it not being clear which is the source view.

## Synchronizing geometries

- **MatchedGeometryProperties**: A set of view properties that may be synchronized between views using the `View.matchedGeometryEffect()` function.
- **GeometryEffect**: An effect that changes the visual appearance of a view, largely without changing its ancestors or descendants.
- **Namespace**: A dynamic property type that allows access to a namespace defined by the persistent identity of the object containing the property (e.g. a view).
- **geometryGroup()**: Isolates the geometry (e.g. position and size) of the view from its parent view.

