--- 来源：https://developer.apple.com/documentation/SwiftUI/View/padding3D(_:_:)

抓取时间：2025-11-30T21:23:36Z

---

# padding3D(_:_:)

**实例方法**

使用您指定的边内边距填充此视图。

## 声明

```swift
nonisolated func padding3D(_ edges: Edge3D.Set = .all, _ length: CGFloat? = nil) -> some View

```

## 参数

- **edges**：要沿此视图内边距填充的边的集合。

- **length**：此视图在每个边上的内边距量。如果为 `nil`，则该量为系统默认值。

## 返回值

一个使用您指定的边内边距填充此视图的视图。

## 为视图添加内边距

- **padding(_:)**：为该视图的每个边缘添加不同的内边距。

- **padding(_:_:)**：为该视图的特定边缘添加相等的内边距。

- **padding3D(_:)**：使用您指定的边内边距为该视图添加内边距。

- **scenePadding(_:)**：使用适合当前场景的内边距，为该视图的指定边缘添加内边距。

- **scenePadding(_:edges:)**：使用适合当前场景的内边距，为该视图的指定边缘添加指定类型的内边距。

- **ScenePadding**：用于将视图与其包含场景分隔开的内边距。


---
source: https://developer.apple.com/documentation/SwiftUI/View/padding3D(_:_:)
crawled: 2025-11-30T21:23:36Z
---

# padding3D(_:_:)

**Instance Method**

Pads this view using the edge insets you specify.

## Declaration

```swift
nonisolated func padding3D(_ edges: Edge3D.Set = .all, _ length: CGFloat? = nil) -> some View

```

## Parameters

- **edges**: The set of edges along which to inset this view.
- **length**: The amount to inset this view on each edge. If `nil`, the amount is the system default amount.

## Return Value

A view that pads this view using edge the insets you specify.

## Adding padding around a view

- **padding(_:)**: Adds a different padding amount to each edge of this view.
- **padding(_:_:)**: Adds an equal padding amount to specific edges of this view.
- **padding3D(_:)**: Pads this view using the edge insets you specify.
- **scenePadding(_:)**: Adds padding to the specified edges of this view using an amount that’s appropriate for the current scene.
- **scenePadding(_:edges:)**: Adds a specified kind of padding to the specified edges of this view using an amount that’s appropriate for the current scene.
- **ScenePadding**: The padding used to space a view from its containing scene.

