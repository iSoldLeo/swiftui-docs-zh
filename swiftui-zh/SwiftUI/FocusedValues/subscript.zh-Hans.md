--- 来源：https://developer.apple.com/documentation/SwiftUI/FocusedValues/subscript(_:)

抓取时间：2025-12-01T11:37:07Z

---

# subscript(_:)

**实例下标**

读取和写入与给定焦点值键关联的值。

## 声明

```swift
subscript<Key>(key: Key.Type) -> Key.Value? where Key : FocusedValueKey { get set }
```

## 概述

使用此下标获取或设置自定义 [FocusedValueKey](../FocusedValueKey.zh-Hans.md) 的焦点值。在大多数情况下，您将使用 `Entry` 宏来创建焦点值属性，该宏会自动生成相应的键并在内部使用此下标：

```swift
extension FocusedValues {
    @Entry var myCustomValue: MyType?
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/FocusedValues/subscript(_:)
crawled: 2025-12-01T11:37:07Z
---

# subscript(_:)

**Instance Subscript**

Reads and writes values associated with a given focused value key.

## Declaration

```swift
subscript<Key>(key: Key.Type) -> Key.Value? where Key : FocusedValueKey { get set }
```

## Overview

Use this subscript to get or set a focused value for a custom [FocusedValueKey](../FocusedValueKey.zh-Hans.md). In most cases, you’ll use the `Entry` macro to create focused value properties, which automatically generates the appropriate key and uses this subscript internally:

```swift
extension FocusedValues {
    @Entry var myCustomValue: MyType?
}
```

