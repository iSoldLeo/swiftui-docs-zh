--- 来源：https://developer.apple.com/documentation/SwiftUI/View/equatable()

抓取时间：2025-11-30T19:48:42Z

---

# equatable()

**实例方法**

防止视图在子视图的新值与其旧值相同时更新子视图。

## 声明

```swift
nonisolated func equatable() -> EquatableView<Self>
```

## 管理视图层级

- **id(_:)**：将视图的标识绑定到给定的代理值。

- **tag(_:includeOptional:)**：设置此视图的唯一标签值。


---
source: https://developer.apple.com/documentation/SwiftUI/View/equatable()
crawled: 2025-11-30T19:48:42Z
---

# equatable()

**Instance Method**

Prevents the view from updating its child view when its new value is the same as its old value.

## Declaration

```swift
nonisolated func equatable() -> EquatableView<Self>
```

## Managing the view hierarchy

- **id(_:)**: Binds a view’s identity to the given proxy value.
- **tag(_:includeOptional:)**: Sets the unique tag value of this view.

