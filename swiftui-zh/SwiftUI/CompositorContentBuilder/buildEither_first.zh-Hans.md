---
来源：https://developer.apple.com/documentation/SwiftUI/CompositorContentBuilder/buildEither(first:)
抓取时间： 2025-12-01T11:22:13Z
---

# buildEither(first:)

**类型方法**

当条件为真时，为多语句闭包中的条件语句生成内容。

### 声明

```swift
static func buildEither<F>(first: _ConditionalContent<_LimitedAvailabilityCompositorContent, _LimitedAvailabilityCompositorContent>) -> _ConditionalContent<_LimitedAvailabilityCompositorContent, F> where F : CompositorContent
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
source: https://developer.apple.com/documentation/SwiftUI/CompositorContentBuilder/buildEither(first:)
crawled: 2025-12-01T11:22:13Z
---

# buildEither(first:)

**Type Method**

Produces content for a conditional statement in a multi-statement closure when the condition is true.

## Declaration

```swift
static func buildEither<F>(first: _ConditionalContent<_LimitedAvailabilityCompositorContent, _LimitedAvailabilityCompositorContent>) -> _ConditionalContent<_LimitedAvailabilityCompositorContent, F> where F : CompositorContent
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

