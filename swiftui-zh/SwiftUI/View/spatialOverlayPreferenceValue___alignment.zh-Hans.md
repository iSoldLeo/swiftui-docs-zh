--- 来源：https://developer.apple.com/documentation/SwiftUI/View/spatialOverlayPreferenceValue(_:alignment:_:)

抓取时间：2025-12-02T17:25:24Z

---

# spatialOverlayPreferenceValue(_:alignment:_:)

**实例方法**

使用视图中指定的偏好值，生成另一个视图，该视图占据与第一个视图相同的 3D 空间。

## 声明

```swift
nonisolated func spatialOverlayPreferenceValue<K, V>(_ key: K.Type, alignment: Alignment3D = .center, @ViewBuilder _ transform: @escaping (K.Value) -> V) -> some View where K : PreferenceKey, V : View

```


---
source: https://developer.apple.com/documentation/SwiftUI/View/spatialOverlayPreferenceValue(_:alignment:_:)
crawled: 2025-12-02T17:25:24Z
---

# spatialOverlayPreferenceValue(_:alignment:_:)

**Instance Method**

Uses the specified preference value from the view to produce another view occupying the same 3D space of the first view.

## Declaration

```swift
nonisolated func spatialOverlayPreferenceValue<K, V>(_ key: K.Type, alignment: Alignment3D = .center, @ViewBuilder _ transform: @escaping (K.Value) -> V) -> some View where K : PreferenceKey, V : View

```

