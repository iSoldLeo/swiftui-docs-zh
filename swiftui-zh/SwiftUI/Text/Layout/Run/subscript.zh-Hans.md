--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/Layout/Run/subscript(_:)

抓取时间：2025-12-05T08:32:36Z

---

# subscript(_:)

**实例 Subscript**

与字形序列关联的自定义属性，类型为 `T`，如果为 nil 则为空。如果没有包含该自定义属性的字形序列，我们还会检查其附件的字形序列。

## 声明

```swift
subscript<T>(key: T.Type) -> T? where T : TextAttribute { get }
```


---
source: https://developer.apple.com/documentation/SwiftUI/Text/Layout/Run/subscript(_:)
crawled: 2025-12-05T08:32:36Z
---

# subscript(_:)

**Instance Subscript**

The custom attribute of type `T` associated with the run of glyphs, or nil. If no run contains the custom attribute we also check its attachment’s runs.

## Declaration

```swift
subscript<T>(key: T.Type) -> T? where T : TextAttribute { get }
```

