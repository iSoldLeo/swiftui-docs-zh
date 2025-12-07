--- 来源：https://developer.apple.com/documentation/SwiftUI/SearchSuggestionsPlacement/Set
抓取时间：2025-12-03T06:05:30Z

---

# SearchSuggestionsPlacement.Set

**Structure**

一组高效的搜索建议显示模式。

## 声明

```swift
struct Set
```

## 获取位置集

- **content**：包含应用主内容位置（不包括菜单位置）的集合。

- **menu**：包含菜单显示模式的集合。

## 创建集合

- **init(rawValue:)**：根据整数创建搜索建议集合。

- **rawValue**：记录搜索建议显示模式的原始值。

## 支持的类型

- **SearchSuggestionsPlacement.Set.Element**：集合元素的类型。

## 符合以下类型：

- Equatable

- ExpressibleByArrayLiteral

- OptionSet

- RawRepresentable

- Sendable

- SendableMetatype

- SetAlgebra


---
source: https://developer.apple.com/documentation/SwiftUI/SearchSuggestionsPlacement/Set
crawled: 2025-12-03T06:05:30Z
---

# SearchSuggestionsPlacement.Set

**Structure**

An efficient set of search suggestion display modes.

## Declaration

```swift
struct Set
```

## Getting placement sets

- **content**: A set containing placements with the apps main content, excluding the menu placement.
- **menu**: A set containing the menu display mode.

## Creating a set

- **init(rawValue:)**: Creates a set of search suggestions from an integer.
- **rawValue**: The raw value that records the search suggestion display modes.

## Supporting types

- **SearchSuggestionsPlacement.Set.Element**: A type for the elements of the set.

## Conforms To

- Equatable
- ExpressibleByArrayLiteral
- OptionSet
- RawRepresentable
- Sendable
- SendableMetatype
- SetAlgebra

