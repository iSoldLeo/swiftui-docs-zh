---
来源： https://developer.apple.com/documentation/SwiftUI/TextSelectability/allowsSelection
抓取时间： 2025-12-03T06:17:31Z
---

# allowsSelection

**类型属性**

布尔值，表示选择性类型是否允许选择。

## 声明

```swift
static var allowsSelection: Bool { get }
```

## 讨论

符合要求的类型（如[EnabledTextSelectability](../EnabledTextSelectability.zh-Hans.md) 和 [DisabledTextSelectability](../DisabledTextSelectability.zh-Hans.md)）会根据情况为该属性返回`true` 或 `false`。SwiftUI 希望给定选择性类型的此值是恒定的，不受全局状态的影响。


---
source: https://developer.apple.com/documentation/SwiftUI/TextSelectability/allowsSelection
crawled: 2025-12-03T06:17:31Z
---

# allowsSelection

**Type Property**

A Boolean value that indicates whether the selectability type allows selection.

## Declaration

```swift
static var allowsSelection: Bool { get }
```

## Discussion

Conforming types, such as [EnabledTextSelectability](../EnabledTextSelectability.zh-Hans.md) and [DisabledTextSelectability](../DisabledTextSelectability.zh-Hans.md), return `true` or `false` for this property as appropriate. SwiftUI expects this value for a given selectability type to be constant, unaffected by global state.

