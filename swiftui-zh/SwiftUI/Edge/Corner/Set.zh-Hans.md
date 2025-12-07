---
来源： https://developer.apple.com/documentation/SwiftUI/Edge/Corner/Set
抓取时间： 2025-12-04T13:33:44Z
---

# 边.角.设置

**Structure**

一个有效的角集。

## 声明

```swift
struct Set
```

## Initializers

- **init(_:)**：创建只包含指定角的角集。
- **init(rawValue:)**：创建给定原始值的角集。

### 实例方法

- **contains(_:)**：仅当`corner` 是调用集合的成员时才返回 true。

### 类型属性

- **all**：所有角。
- **bottom**：底部的前角和后角。
- **bottomLeading**：底部前导角。
- **bottomTrailing**：底部的尾角。
- **leading**：顶部和底部的前角。
- **none**：没有角。
- **top**： 无角：顶部的前角和尾角。
- **topLeading**：上前角。
- **topTrailing**：顶部的尾角。
- **trailing**：顶部和底部的尾角。

## 符合

- 可复制
- 自定义调试字符串可转换
- 等价
- 可表达数组字素
- 可散列
- 选项集
- 原始可表示
- 可发送
- 可发送元类
- 代数集


---
source: https://developer.apple.com/documentation/SwiftUI/Edge/Corner/Set
crawled: 2025-12-04T13:33:44Z
---

# Edge.Corner.Set

**Structure**

An efficient set of corners.

## Declaration

```swift
struct Set
```

## Initializers

- **init(_:)**: Creates set of corners containing only the specified corner.
- **init(rawValue:)**: Creates a corner set given a raw value.

## Instance Methods

- **contains(_:)**: Returns true only if `corner` is a member of the calling set.

## Type Properties

- **all**: All corners.
- **bottom**: The bottom leading and trailing corners.
- **bottomLeading**: The bottom leading corner.
- **bottomTrailing**: The bottom trailing corner.
- **leading**: The top and bottom leading corners.
- **none**: No corners.
- **top**: The top leading and trailing corners.
- **topLeading**: The top leading corner.
- **topTrailing**: The top trailing corner.
- **trailing**: The top and bottom trailing corners.

## Conforms To

- Copyable
- CustomDebugStringConvertible
- Equatable
- ExpressibleByArrayLiteral
- Hashable
- OptionSet
- RawRepresentable
- Sendable
- SendableMetatype
- SetAlgebra

