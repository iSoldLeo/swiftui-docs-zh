---
来源： https://developer.apple.com/documentation/SwiftUI/ViewModifier/concat(_:)
抓取时间： 2025-12-02T17:46:20Z
---

# concat(_:)

**实例方法**

返回一个新修饰符，它是`self` 与 `modifier` 连接的结果。

## 声明

```swift
nonisolated func concat<T>(_ modifier: T) -> ModifiedContent<Self, T>
```

## 为视图添加动画

- **animation(_:)**：返回修改器的新版本，该版本会将`animation` 应用于修改器中的所有可动画值。


---
source: https://developer.apple.com/documentation/SwiftUI/ViewModifier/concat(_:)
crawled: 2025-12-02T17:46:20Z
---

# concat(_:)

**Instance Method**

Returns a new modifier that is the result of concatenating `self` with `modifier`.

## Declaration

```swift
nonisolated func concat<T>(_ modifier: T) -> ModifiedContent<Self, T>
```

## Adding animations to a view

- **animation(_:)**: Returns a new version of the modifier that will apply `animation` to all animatable values within the modifier.

