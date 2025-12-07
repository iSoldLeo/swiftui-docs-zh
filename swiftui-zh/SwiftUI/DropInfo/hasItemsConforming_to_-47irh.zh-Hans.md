---
来源：https://developer.apple.com/documentation/SwiftUI/DropInfo/hasItemsConforming(to:)-47irh
抓取时间： 2025-12-01T11:36:46Z
---

# hasItemsConforming(to:)

**实例方法**

指示是否至少有一个项目符合至少一个指定的统一类型标识符。

## 声明

```swift
func hasItemsConforming(to contentTypes: [UTType]) -> Bool
```

## 参数

- **contentTypes**：要查询的统一类型标识符。

## 返回值

是否至少有一个项目符合 `contentTypes`。

## 检查项目

- **itemProviders(for:)**：查找至少符合一个指定的统一类型标识符的项目提供者。


---
source: https://developer.apple.com/documentation/SwiftUI/DropInfo/hasItemsConforming(to:)-47irh
crawled: 2025-12-01T11:36:46Z
---

# hasItemsConforming(to:)

**Instance Method**

Indicates whether at least one item conforms to at least one of the specified uniform type identifiers.

## Declaration

```swift
func hasItemsConforming(to contentTypes: [UTType]) -> Bool
```

## Parameters

- **contentTypes**: The uniform type identifiers to query for.

## Return Value

Whether at least one item conforms to one of `contentTypes`.

## Checking for items

- **itemProviders(for:)**: Finds item providers that conform to at least one of the specified uniform type identifiers.

