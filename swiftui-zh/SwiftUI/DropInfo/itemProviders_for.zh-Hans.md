---
来源：https://developer.apple.com/documentation/SwiftUI/DropInfo/itemProviders(for:)
抓取时间： 2025-12-01T11:36:50Z
---

# itemProviders(for:)

**实例方法**

查找至少符合一个指定的统一类型标识符的项目提供程序。

## 声明

```swift
func itemProviders(for contentTypes: [UTType]) -> [NSItemProvider]
```

## 参数

- **contentTypes**：要查询的统一类型标识符。

## 返回值

符合`contentTypes`的项目提供者。

## 讨论

该函数仅在`performDrop()` 操作中有效。


---
source: https://developer.apple.com/documentation/SwiftUI/DropInfo/itemProviders(for:)
crawled: 2025-12-01T11:36:50Z
---

# itemProviders(for:)

**Instance Method**

Finds item providers that conform to at least one of the specified uniform type identifiers.

## Declaration

```swift
func itemProviders(for contentTypes: [UTType]) -> [NSItemProvider]
```

## Parameters

- **contentTypes**: The uniform type identifiers to query for.

## Return Value

The item providers that conforms to `contentTypes`.

## Discussion

This function is only valid during the `performDrop()` action.

