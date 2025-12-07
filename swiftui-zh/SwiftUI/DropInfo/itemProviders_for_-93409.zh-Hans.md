---
来源：https://developer.apple.com/documentation/SwiftUI/DropInfo/itemProviders(for:)-93409
抓取时间： 2025-12-03T06:47:37Z
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

## 检查项目

- **hasItemsConforming(to:)**：表示是否至少有一个项目符合至少一个指定的统一类型标识符。


---
source: https://developer.apple.com/documentation/SwiftUI/DropInfo/itemProviders(for:)-93409
crawled: 2025-12-03T06:47:37Z
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

## Checking for items

- **hasItemsConforming(to:)**: Indicates whether at least one item conforms to at least one of the specified uniform type identifiers.

