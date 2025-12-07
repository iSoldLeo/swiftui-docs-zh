--- 来源：https://developer.apple.com/documentation/SwiftUI/View/spatialOverlay(alignment:content:)

抓取时间：2025-11-30T21:10:29Z

---

# spatialOverlay(alignment:content:)

**实例方法**

在此视图的 3D 边界内添加辅助视图。

## 声明

```swift
nonisolated func spatialOverlay<V>(alignment: Alignment3D = .center, @ViewBuilder content: () -> V) -> some View where V : View

```

## 参数

- **alignment**：用于定位辅助视图的对齐方式，默认值为 [center](../Alignment3D/center.zh-Hans.md)。

- **content**：用于生成与此视图占据同一 3D 空间的视图的视图构建器。内容提供的多个视图将组织成一个 [SpatialContainer](../SpatialContainer.zh-Hans.md)。

## 返回值

在视图的 3D 边界内添加 `content` 的视图。

## 说明

由 `content` 提供的多个视图按深度方向堆叠。


---
source: https://developer.apple.com/documentation/SwiftUI/View/spatialOverlay(alignment:content:)
crawled: 2025-11-30T21:10:29Z
---

# spatialOverlay(alignment:content:)

**Instance Method**

Adds secondary views within the 3D bounds of this view.

## Declaration

```swift
nonisolated func spatialOverlay<V>(alignment: Alignment3D = .center, @ViewBuilder content: () -> V) -> some View where V : View

```

## Parameters

- **alignment**: The alignment with a default value of [center](../Alignment3D/center.zh-Hans.md) that you use to position the secondary view.
- **content**: The view builder which produces views to occupy the same 3D space as this view. Multiple views provided by content are organized into a [SpatialContainer](../SpatialContainer.zh-Hans.md).

## Return Value

A view that adds `content` within the view’s 3D bounds.

## Discussion

Multiple views provided by `content` are stacked depthwise.

