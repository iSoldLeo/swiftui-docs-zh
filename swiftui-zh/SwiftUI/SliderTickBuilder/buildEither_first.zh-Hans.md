---
来源：https://developer.apple.com/documentation/SwiftUI/SliderTickBuilder/buildEither(first:)
抓取时间： 2025-12-02T01:12:15Z
---

# buildEither(first:)

**类型方法**

当条件为真时，为多语句闭包中的条件语句生成内容。

### 声明

```swift
static func buildEither<T, F>(first: T) -> _ConditionalContent<T, F> where V == T.Value, T : SliderTickContent, F : SliderTickContent, T.Body == F.Body
```


---
source: https://developer.apple.com/documentation/SwiftUI/SliderTickBuilder/buildEither(first:)
crawled: 2025-12-02T01:12:15Z
---

# buildEither(first:)

**Type Method**

Produces content for a conditional statement in a multi-statement closure when the condition is true.

## Declaration

```swift
static func buildEither<T, F>(first: T) -> _ConditionalContent<T, F> where V == T.Value, T : SliderTickContent, F : SliderTickContent, T.Body == F.Body
```

