--- 来源：https://developer.apple.com/documentation/SwiftUI/View/id(_:)

抓取时间：2025-12-02T16:02:41Z

---

# id(_:)

**实例方法**

将视图的标识绑定到给定的代理值。

## 声明

```swift
nonisolated func id<ID>(_ id: ID) -> some View where ID : Hashable

```

## 说明

当 `id` 参数指定的代理值发生变化时，视图的标识（例如其状态）将被重置。

## 管理视图层级

- **tag(_:includeOptional:)**：设置此视图的唯一标签值。

- **equatable()**：防止视图在新值与其旧值相同时更新其子视图。


---
source: https://developer.apple.com/documentation/SwiftUI/View/id(_:)
crawled: 2025-12-02T16:02:41Z
---

# id(_:)

**Instance Method**

Binds a view’s identity to the given proxy value.

## Declaration

```swift
nonisolated func id<ID>(_ id: ID) -> some View where ID : Hashable

```

## Discussion

When the proxy value specified by the `id` parameter changes, the identity of the view — for example, its state — is reset.

## Managing the view hierarchy

- **tag(_:includeOptional:)**: Sets the unique tag value of this view.
- **equatable()**: Prevents the view from updating its child view when its new value is the same as its old value.

