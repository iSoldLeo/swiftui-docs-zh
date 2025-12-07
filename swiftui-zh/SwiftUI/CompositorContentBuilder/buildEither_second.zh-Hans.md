---
来源：https://developer.apple.com/documentation/SwiftUI/CompositorContentBuilder/buildEither(Second:)
抓取时间：2025-12-03T06:33:03Z
---

# buildEither(second:)

**类型方法**

当条件为假时，为多语句闭包中的条件语句生成内容。

### 声明

```swift
static func buildEither<F>(second: F) -> _ConditionalContent<_LimitedAvailabilityCompositorContent, F> where F : CompositorContent
```

## 讨论

[CompositorContentBuilder](../CompositorContentBuilder.zh-Hans.md)中的条件语句必须同时包含`if`语句和`else`语句，而且条件只能执行编译器的可用性检查，如下面的代码：

```swift
var body: some CompositorContent {
    if #available(visionOS 100, *) {
        MyNewContent()
    } else {
        MyOldContent()
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/CompositorContentBuilder/buildEither(second:)
crawled: 2025-12-03T06:33:03Z
---

# buildEither(second:)

**Type Method**

Produces content for a conditional statement in a multi-statement closure when the condition is false.

## Declaration

```swift
static func buildEither<F>(second: F) -> _ConditionalContent<_LimitedAvailabilityCompositorContent, F> where F : CompositorContent
```

## Discussion

Conditional statements in a [CompositorContentBuilder](../CompositorContentBuilder.zh-Hans.md) must contain both an `if` statement and an `else` statement, and the condition can only perform a compiler check for availability, like in the following code:

```swift
var body: some CompositorContent {
    if #available(visionOS 100, *) {
        MyNewContent()
    } else {
        MyOldContent()
    }
}
```

