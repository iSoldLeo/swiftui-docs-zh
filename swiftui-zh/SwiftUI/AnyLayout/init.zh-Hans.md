---
来源： https://developer.apple.com/documentation/SwiftUI/AnyLayout/init(_:)
抓取时间： 2025-12-01T11:28:54Z
---

# init(_:)

**Initializer**

创建封装指定布局的类型抹除值。

### 声明

```swift
init<L>(_ layout: L) where L : Layout
```

## 讨论

您可以在不丢失子视图状态的情况下在类型擦除布局之间切换。


---
source: https://developer.apple.com/documentation/SwiftUI/AnyLayout/init(_:)
crawled: 2025-12-01T11:28:54Z
---

# init(_:)

**Initializer**

Creates a type-erased value that wraps the specified layout.

## Declaration

```swift
init<L>(_ layout: L) where L : Layout
```

## Discussion

You can switch between type-erased layouts without losing the state of the subviews.

