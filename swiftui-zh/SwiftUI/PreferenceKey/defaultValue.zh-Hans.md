---
来源： https://developer.apple.com/documentation/SwiftUI/PreferenceKey/defaultValue
抓取时间： 2025-12-03T06:08:24Z
---

# defaultValue

**类型属性**

偏好设置的默认值。

## 声明

```swift
static var defaultValue: Self.Value { get }
```

## 讨论

没有显式键值的视图会产生此默认值。组合子视图可能会移除使用默认值产生的隐含值。这意味着`reduce(value: &x, nextValue: {defaultValue})` 不应改变`x` 的含义。

## 获取默认值

- **Value**：此偏置产生的值的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/PreferenceKey/defaultValue
crawled: 2025-12-03T06:08:24Z
---

# defaultValue

**Type Property**

The default value of the preference.

## Declaration

```swift
static var defaultValue: Self.Value { get }
```

## Discussion

Views that have no explicit value for the key produce this default value. Combining child views may remove an implicit value produced by using the default. This means that `reduce(value: &x, nextValue: {defaultValue})` shouldn’t change the meaning of `x`.

## Getting the default value

- **Value**: The type of value produced by this preference.

