---
来源： https://developer.apple.com/documentation/SwiftUI/ViewModifier/transaction(_:)
抓取时间： 2025-11-30T21:31:16Z
---

# transaction(_:)

**实例方法**

返回修改器的新版本，该版本将对修改器中的所有事务应用事务突变函数`transform`。

### 声明

```swift
nonisolated func transaction(_ transform: @escaping (inout Transaction) -> Void) -> some ViewModifier

```


---
source: https://developer.apple.com/documentation/SwiftUI/ViewModifier/transaction(_:)
crawled: 2025-11-30T21:31:16Z
---

# transaction(_:)

**Instance Method**

Returns a new version of the modifier that will apply the transaction mutation function `transform` to all transactions within the modifier.

## Declaration

```swift
nonisolated func transaction(_ transform: @escaping (inout Transaction) -> Void) -> some ViewModifier

```

