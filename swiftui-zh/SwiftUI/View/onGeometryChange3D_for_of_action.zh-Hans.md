--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onGeometryChange3D(for:of:action:)

抓取时间：2025-11-30T21:10:03Z

---

# onGeometryChange3D(for:of:action:)

**实例方法**

返回一个新的视图，该视图会在 `transform(proxy)` 计算出的值发生变化时调用 `action(value)`，其中 `proxy` 提供对视图 3D 几何属性的访问。

## 声明

```swift
@MainActor @preconcurrency func onGeometryChange3D<T>(for type: T.Type, of transform: @escaping (GeometryProxy3D) -> T, action: @escaping (T) -> Void) -> some View where T : Equatable

```


---
source: https://developer.apple.com/documentation/SwiftUI/View/onGeometryChange3D(for:of:action:)
crawled: 2025-11-30T21:10:03Z
---

# onGeometryChange3D(for:of:action:)

**Instance Method**

Returns a new view that arranges to call `action(value)` whenever the value computed by `transform(proxy)` changes, where `proxy` provides access to the view’s 3D geometry properties.

## Declaration

```swift
@MainActor @preconcurrency func onGeometryChange3D<T>(for type: T.Type, of transform: @escaping (GeometryProxy3D) -> T, action: @escaping (T) -> Void) -> some View where T : Equatable

```

