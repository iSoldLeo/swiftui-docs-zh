---
来源：https://developer.apple.com/documentation/SwiftUI/PreferenceKey/reduce(value:nextValue:)
抓取时间： 2025-12-03T06:08:25Z
---

# reduce(value:nextValue:)

**类型方法**

通过用提供下一个值的闭包结果修改之前累积的值来组合一个值序列。

### 声明

```swift
static func reduce(value: inout Self.Value, nextValue: () -> Self.Value)
```

## 参数

- **value**：以前调用本方法时累积的值。执行时应修改该值。
- **nextValue**：返回序列中下一个值的闭包。

## 讨论

本方法按视图树顺序接收值。从概念上讲，这是将一棵树的偏好值与其下一棵树的偏好值结合起来。


---
source: https://developer.apple.com/documentation/SwiftUI/PreferenceKey/reduce(value:nextValue:)
crawled: 2025-12-03T06:08:25Z
---

# reduce(value:nextValue:)

**Type Method**

Combines a sequence of values by modifying the previously-accumulated value with the result of a closure that provides the next value.

## Declaration

```swift
static func reduce(value: inout Self.Value, nextValue: () -> Self.Value)
```

## Parameters

- **value**: The value accumulated through previous calls to this method. The implementation should modify this value.
- **nextValue**: A closure that returns the next value in the sequence.

## Discussion

This method receives its values in view-tree order. Conceptually, this combines the preference value from one tree with that of its next sibling.

