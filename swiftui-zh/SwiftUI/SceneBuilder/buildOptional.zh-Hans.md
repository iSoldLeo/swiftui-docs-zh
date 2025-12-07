--- 来源：https://developer.apple.com/documentation/SwiftUI/SceneBuilder/buildOptional(_:)

抓取时间：2025-12-03T05:31:13Z

---

# buildOptional(_:)

**类型方法**

为多语句闭包中的条件语句生成一个可选场景，该场景仅在条件为真时可见。

## 声明

```swift
static func buildOptional(_ scene: (any Scene & _LimitedAvailabilitySceneMarker)?) -> some Scene

```

## 讨论

[SceneBuilder](../SceneBuilder.zh-Hans.md) 中的条件语句可以包含 `if` 语句，但不能包含 `else` 语句。该条件只能执行编译器可用性检查，例如以下代码：

```swift
var body: some Scene {
    if #available(iOS 16, *) {
        WindowGroup {
            ContentView()
        }
    }
}
```

## 构建内容

- **buildBlock(_:)**：将作为子场景编写的单个场景原封不动地传递。

- **buildExpression(_:)**：在构建器中构建表达式。

- **buildLimitedAvailability(_:)**：处理场景内容，查找执行可用性检查的条件编译器控制语句。


---
source: https://developer.apple.com/documentation/SwiftUI/SceneBuilder/buildOptional(_:)
crawled: 2025-12-03T05:31:13Z
---

# buildOptional(_:)

**Type Method**

Produces an optional scene for conditional statements in multi-statement closures that’s only visible when the condition evaluates to true.

## Declaration

```swift
static func buildOptional(_ scene: (any Scene & _LimitedAvailabilitySceneMarker)?) -> some Scene

```

## Discussion

Conditional statements in a [SceneBuilder](../SceneBuilder.zh-Hans.md) can contain an `if` statement but not an `else` statement, and the condition can only perform a compiler check for availability, like in the following code:

```swift
var body: some Scene {
    if #available(iOS 16, *) {
        WindowGroup {
            ContentView()
        }
    }
}
```

## Building content

- **buildBlock(_:)**: Passes a single scene written as a child scene through unmodified.
- **buildExpression(_:)**: Builds an expression within the builder.
- **buildLimitedAvailability(_:)**: Processes scene content for a conditional compiler-control statement that performs an availability check.

