--- 来源：https://developer.apple.com/documentation/SwiftUI/View/writingDirection(strategy:)

抓取时间：2025-12-02T17:26:27Z

---

# writingDirection(strategy:)

**实例方法**

用于修饰视图层级结构中默认文本书写方向策略的参数。

## 声明

```swift
nonisolated func writingDirection(strategy: Text.WritingDirectionStrategy) -> some View

```

## 说明

要显式控制书写方向，请选择 [layoutBased](../Text/WritingDirectionStrategy/layoutBased.zh-Hans.md) 模式，并将 [layoutDirection](../EnvironmentValues/layoutDirection.zh-Hans.md) 设置为相应的值。


---
source: https://developer.apple.com/documentation/SwiftUI/View/writingDirection(strategy:)
crawled: 2025-12-02T17:26:27Z
---

# writingDirection(strategy:)

**Instance Method**

A modifier for the default text writing direction strategy in the view hierarchy.

## Declaration

```swift
nonisolated func writingDirection(strategy: Text.WritingDirectionStrategy) -> some View

```

## Discussion

To control the writing direction explicitly, choose the [layoutBased](../Text/WritingDirectionStrategy/layoutBased.zh-Hans.md) mode and set the [layoutDirection](../EnvironmentValues/layoutDirection.zh-Hans.md) to the appropriate value.

