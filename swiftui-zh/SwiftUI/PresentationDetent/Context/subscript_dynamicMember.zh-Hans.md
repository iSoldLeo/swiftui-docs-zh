---
来源： https://developer.apple.com/documentation/SwiftUI/PresentationDetent/Context/subscript(dynamicMember:)
抓取时间： 2025-12-04T13:08:40Z
---

# subscript(dynamicMember:)

**实例下标**

从环境中返回 keyPath 指定的值。

## 声明

```swift
subscript<T>(dynamicMember keyPath: KeyPath<EnvironmentValues, T>) -> T { get }
```

## 概览

这使用的是显示工作表的环境，而不是应用演示修改器的环境。


---
source: https://developer.apple.com/documentation/SwiftUI/PresentationDetent/Context/subscript(dynamicMember:)
crawled: 2025-12-04T13:08:40Z
---

# subscript(dynamicMember:)

**Instance Subscript**

Returns the value specified by the keyPath from the environment.

## Declaration

```swift
subscript<T>(dynamicMember keyPath: KeyPath<EnvironmentValues, T>) -> T { get }
```

## Overview

This uses the environment from where the sheet is shown, not the environment where the presentation modifier is applied.

