---
来源： https://developer.apple.com/documentation/SwiftUI/ScrollViewProxy/scrollTo(_:anchor:)
抓取时间： 2025-12-01T11:31:07Z
---

# scrollTo(_:anchor:)

**实例方法**

扫描代理包含的所有滚动视图，查找第一个带有标识符`id`的子视图，然后滚动到该视图。

## 声明

```swift
func scrollTo<ID>(_ id: ID, anchor: UnitPoint? = nil) where ID : Hashable
```

## 参数

- **id**：要滚动到的子视图的标识符。
- **anchor**：滚动操作的对齐行为。

## 讨论

如果 `anchor` 是 `nil`，本方法会找到所识别视图的容器，并滚动最小的滚动量，使所识别的视图完全可见。

如果`anchor` 不是`nil`，它将定义已识别视图中与滚动视图对齐的点。例如，将`anchor` 设置为[top](../UnitPoint/top.zh-Hans.md)，可使识别视图的顶部与滚动视图的顶部对齐。同样，将 `anchor` 设置为 [bottom](../UnitPoint/bottom.zh-Hans.md)，可使已识别视图的底部与滚动视图的底部对齐，依此类推。


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollViewProxy/scrollTo(_:anchor:)
crawled: 2025-12-01T11:31:07Z
---

# scrollTo(_:anchor:)

**Instance Method**

Scans all scroll views contained by the proxy for the first with a child view with identifier `id`, and then scrolls to that view.

## Declaration

```swift
func scrollTo<ID>(_ id: ID, anchor: UnitPoint? = nil) where ID : Hashable
```

## Parameters

- **id**: The identifier of a child view to scroll to.
- **anchor**: The alignment behavior of the scroll action.

## Discussion

If `anchor` is `nil`, this method finds the container of the identified view, and scrolls the minimum amount to make the identified view wholly visible.

If `anchor` is non-`nil`, it defines the points in the identified view and the scroll view to align. For example, setting `anchor` to [top](../UnitPoint/top.zh-Hans.md) aligns the top of the identified view to the top of the scroll view. Similarly, setting `anchor` to [bottom](../UnitPoint/bottom.zh-Hans.md) aligns the bottom of the identified view to the bottom of the scroll view, and so on.

