---
来源： https://developer.apple.com/documentation/SwiftUI/ViewBuilder/buildIf(_:)
抓取时间： 2025-11-30T21:31:11Z
---

# buildIf(_:)

**类型 方法**

为多语句闭包中的条件语句生成一个可选视图，该视图仅在条件求值为 true 时可见。

### 声明

```swift
static func buildIf<Content>(_ content: Content?) -> Content? where Content : View
```

## 有条件地构建内容

- **buildEither(first:)**：当条件为真时，为多语句闭包中的条件语句生成内容。
- **buildEither(second:)**：当条件为假时，为多语句闭包中的条件语句生成内容。
- **buildLimitedAvailability(_:)**：处理执行可用性检查的条件编译器控制语句的视图内容。


---
source: https://developer.apple.com/documentation/SwiftUI/ViewBuilder/buildIf(_:)
crawled: 2025-11-30T21:31:11Z
---

# buildIf(_:)

**Type Method**

Produces an optional view for conditional statements in multi-statement closures that’s only visible when the condition evaluates to true.

## Declaration

```swift
static func buildIf<Content>(_ content: Content?) -> Content? where Content : View
```

## Conditionally building content

- **buildEither(first:)**: Produces content for a conditional statement in a multi-statement closure when the condition is true.
- **buildEither(second:)**: Produces content for a conditional statement in a multi-statement closure when the condition is false.
- **buildLimitedAvailability(_:)**: Processes view content for a conditional compiler-control statement that performs an availability check.

