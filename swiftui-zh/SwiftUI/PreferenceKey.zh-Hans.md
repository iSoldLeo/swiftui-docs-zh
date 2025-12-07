--- 来源：https://developer.apple.com/documentation/SwiftUI/PreferenceKey
抓取时间：2025-12-02T17:32:29Z

---

# PreferenceKey

**Protocol**

视图生成的命名值。

## 声明

```swift
protocol PreferenceKey
```

## 概述

具有多个子视图的视图会自动将给定首选项的子视图值合并为一个对其父视图可见的单个值。

## 获取默认值

- **defaultValue**：首选项的默认值。

- **Value**：此首选项生成的值的类型。

## 合并偏好设置

- **reduce(value:nextValue:)**：通过将先前累积的值与提供下一个值的闭包的结果进行修改，来合并一系列值。

## 符合规范的类型

- PreferredColorSchemeKey

- Text.LayoutKey


---
source: https://developer.apple.com/documentation/SwiftUI/PreferenceKey
crawled: 2025-12-02T17:32:29Z
---

# PreferenceKey

**Protocol**

A named value produced by a view.

## Declaration

```swift
protocol PreferenceKey
```

## Overview

A view with multiple children automatically combines its values for a given preference into a single value visible to its ancestors.

## Getting the default value

- **defaultValue**: The default value of the preference.
- **Value**: The type of value produced by this preference.

## Combining preferences

- **reduce(value:nextValue:)**: Combines a sequence of values by modifying the previously-accumulated value with the result of a closure that provides the next value.

## Conforming Types

- PreferredColorSchemeKey
- Text.LayoutKey

