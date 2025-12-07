---
来源：https://developer.apple.com/documentation/SwiftUI/SliderTickBuilder/buildEither(Second:)
抓取时间：2025-12-03T20:27:11Z
---

# buildEither(second:)

**类型方法**

当条件为假时，为多语句闭包中的条件语句生成内容。

### 声明

```swift
static func buildEither<T, F>(second: F) -> _ConditionalContent<T, F> where V == T.Value, T : SliderTickContent, F : SliderTickContent, T.Body == F.Body
```


---
source: https://developer.apple.com/documentation/SwiftUI/SliderTickBuilder/buildEither(second:)
crawled: 2025-12-03T20:27:11Z
---

# buildEither(second:)

**Type Method**

Produces content for a conditional statement in a multi-statement closure when the condition is false.

## Declaration

```swift
static func buildEither<T, F>(second: F) -> _ConditionalContent<T, F> where V == T.Value, T : SliderTickContent, F : SliderTickContent, T.Body == F.Body
```

