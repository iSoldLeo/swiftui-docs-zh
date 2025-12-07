---
来源：https://developer.apple.com/documentation/SwiftUI/DropInfo/itemProviders(for:)-b6fo
抓取时间： 2025-12-01T11:36:48Z
---

# itemProviders(for:)

**实例方法**

返回一个项目数组，每个项目至少符合一个指定的统一类型标识符。

## 声明

```swift
func itemProviders(for types: [String]) -> [NSItemProvider]
```

## 讨论

该函数仅在`performDrop()` 操作期间有效。

## 过时的符号

- **hasItemsConforming(to:)**：返回是否至少有一个项目符合至少一个指定的统一类型标识符。


---
source: https://developer.apple.com/documentation/SwiftUI/DropInfo/itemProviders(for:)-b6fo
crawled: 2025-12-01T11:36:48Z
---

# itemProviders(for:)

**Instance Method**

Returns an array of items that each conform to at least one of the specified uniform type identifiers.

## Declaration

```swift
func itemProviders(for types: [String]) -> [NSItemProvider]
```

## Discussion

This function is only valid during the `performDrop()` action.

## Deprecated symbols

- **hasItemsConforming(to:)**: Returns whether at least one item conforms to at least one of the specified uniform type identifiers.

