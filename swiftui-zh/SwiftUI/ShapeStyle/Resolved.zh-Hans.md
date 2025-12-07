--- 来源：https://developer.apple.com/documentation/SwiftUI/ShapeStyle/Resolved
抓取时间：2025-12-03T06:25:30Z

---

# 已解析

**关联类型**

此形状样式将解析为的类型。

## 声明

```swift
associatedtype Resolved : ShapeStyle = Never
```

## 讨论

创建自定义形状样式时，Swift 会根据您对所需 `resolve` 函数的实现来推断此类型。

## 在环境中解析形状样式

- **resolve(in:)**：根据当前的 `environment` 计算已解析的形状样式。


---
source: https://developer.apple.com/documentation/SwiftUI/ShapeStyle/Resolved
crawled: 2025-12-03T06:25:30Z
---

# Resolved

**Associated Type**

The type of shape style this will resolve to.

## Declaration

```swift
associatedtype Resolved : ShapeStyle = Never
```

## Discussion

When you create a custom shape style, Swift infers this type from your implementation of the required `resolve` function.

## Resolving a shape style in an environment

- **resolve(in:)**: Evaluate to a resolved shape style given the current `environment`.

