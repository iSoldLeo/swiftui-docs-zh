---
来源： https://developer.apple.com/documentation/SwiftUI/PreviewContext/subscript(_:)
抓取时间： 2025-12-03T07:07:34Z
---

# 下标(_:)

**实例下标**

返回上下文中键的值，如果上下文没有定义键的值，则返回键的默认值。

## 声明

```swift
subscript<Key>(key: Key.Type) -> Key.Value where Key : PreviewContextKey { get }
```


---
source: https://developer.apple.com/documentation/SwiftUI/PreviewContext/subscript(_:)
crawled: 2025-12-03T07:07:34Z
---

# subscript(_:)

**Instance Subscript**

Returns the context’s value for a key, or a the key’s default value if the context doesn’t define a value for the key.

## Declaration

```swift
subscript<Key>(key: Key.Type) -> Key.Value where Key : PreviewContextKey { get }
```

