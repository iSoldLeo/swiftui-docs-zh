---
来源：https://developer.apple.com/documentation/SwiftUI/ScrollTargetBehavior/updateTarget(_:context:)
抓取时间：2025-12-03T06:42:12Z
---

# updateTarget(_:context:)

**实例方法**

更新可滚动视图应滚动到的建议目标。

## 声明

```swift
func updateTarget(_ target: inout ScrollTarget, context: Self.TargetContext)
```

## 讨论

系统主要在两种情况下调用此方法：

- 当滚动手势结束时，系统会使用其减速率计算出自然滚动到的位置。系统会提供这个计算值作为本方法的目标值。
- 当滚动视图的大小发生变化时，系统会根据新的大小计算应该滚动到的位置，并将计算值作为本方法的目标值。

您可以使用此方法来覆盖计算出的目标值，这样可滚动视图就会滚动到与原来不同的位置。

## 更新建议目标

- **ScrollTargetBehavior.TargetContext**：滚动行为更新滚动目标的上下文。


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollTargetBehavior/updateTarget(_:context:)
crawled: 2025-12-03T06:42:12Z
---

# updateTarget(_:context:)

**Instance Method**

Updates the proposed target that a scrollable view should scroll to.

## Declaration

```swift
func updateTarget(_ target: inout ScrollTarget, context: Self.TargetContext)
```

## Discussion

The system calls this method in two main cases:

- When a scroll gesture ends, it calculates where it would naturally scroll to using its deceleration rate. The system provides this calculated value as the target of this method.
- When a scrollable view’s size changes, it calculates where it should be scrolled given the new size and provides this calculates value as the target of this method.

You can implement this method to override the calculated target which will have the scrollable view scroll to a different position than it would otherwise.

## Updating the proposed target

- **ScrollTargetBehavior.TargetContext**: The context in which a scroll behavior updates the scroll target.

