--- 来源：https://developer.apple.com/documentation/SwiftUI/View/scaleEffect(_:anchor:)-7q7as

抓取时间：2025-11-30T20:06:44Z

---

# scaleEffect(_:anchor:)

**实例方法**

根据给定的垂直和水平缩放比例，相对于锚点缩放此视图的渲染输出。

## 声明

```swift
nonisolated func scaleEffect(_ scale: CGSize, anchor: UnitPoint = .center) -> some View

```

## 参数

- **scale**：一个 [doc://com.apple.documentation/documentation/CoreFoundation/CGSize] 值，表示要缩放视图的水平和垂直比例。

- **anchor**：一个点，默认值为 [center](../UnitPoint/center.zh-Hans.md)，用于定义在视图中应用变换的位置。

## 讨论

使用 `scaleEffect(_:anchor:)` 可通过应用由 `scale` 指定的特定大小的缩放变换来缩放视图。

```swift
Image(systemName: "envelope.badge.fill")
    .resizable()
    .frame(width: 100, height: 100, alignment: .center)
    .foregroundColor(Color.red)
    .scaleEffect(CGSize(x: 0.9, y: 1.3), anchor: .leading)
    .border(Color.gray)
```


---
source: https://developer.apple.com/documentation/SwiftUI/View/scaleEffect(_:anchor:)-7q7as
crawled: 2025-11-30T20:06:44Z
---

# scaleEffect(_:anchor:)

**Instance Method**

Scales this view’s rendered output by the given vertical and horizontal size amounts, relative to an anchor point.

## Declaration

```swift
nonisolated func scaleEffect(_ scale: CGSize, anchor: UnitPoint = .center) -> some View

```

## Parameters

- **scale**: A [doc://com.apple.documentation/documentation/CoreFoundation/CGSize] that represents the horizontal and vertical amount to scale the view.
- **anchor**: The point with a default of [center](../UnitPoint/center.zh-Hans.md) that defines the location within the view from which to apply the transformation.

## Discussion

Use `scaleEffect(_:anchor:)` to scale a view by applying a scaling transform of a specific size, specified by `scale`.

```swift
Image(systemName: "envelope.badge.fill")
    .resizable()
    .frame(width: 100, height: 100, alignment: .center)
    .foregroundColor(Color.red)
    .scaleEffect(CGSize(x: 0.9, y: 1.3), anchor: .leading)
    .border(Color.gray)
```



