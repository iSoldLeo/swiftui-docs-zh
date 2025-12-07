---
来源： https://developer.apple.com/documentation/SwiftUI/Transaction/scrollTargetAnchor
抓取时间： 2025-12-03T06:17:24Z
---

# scrollTargetAnchor

**实例属性**

滚动到某个视图时，视图在滚动视图可见区域内的首选对齐方式。

## 声明

```swift
var scrollTargetAnchor: UnitPoint? { get set }
```

## 讨论

将此 API 与 `ScrollViewProxy/scrollTo(_:anchor)` 结合使用，或在更新提供给 [scrollPosition(id:anchor:)](../View/scrollPosition_id_anchor.zh-Hans.md) 的绑定时使用。

```swift
@Binding var position: Item.ID?

var body: some View {
    ScrollView {
        LazyVStack {
            ForEach(items) { item in
                ItemView(item)
            }
        }
        .scrollTargetLayout()
    }
    .scrollPosition(id: $position)
    .safeAreaInset(edge: .bottom) {
        Button("Scroll To Bottom") {
            withAnimation {
                withTransaction(\.scrollTargetAnchor, .bottom) {
                    position = items.last?.id
                }
            }
        }
    }
}
```

与[scrollPosition(id:anchor:)](../View/scrollPosition_id_anchor.zh-Hans.md)修改器一起使用时，该值将优先于修改器中为当前事务指定的锚点。

## 获取事务信息

- **isContinuous**：布尔值，表示该事务是否源于产生一连串值的操作。
- **tracksVelocity**：该事务是否会跟踪任何动画属性变化的速度。
- **subscript(_:)**：访问与自定义键关联的事务值。


---
source: https://developer.apple.com/documentation/SwiftUI/Transaction/scrollTargetAnchor
crawled: 2025-12-03T06:17:24Z
---

# scrollTargetAnchor

**Instance Property**

The preferred alignment of the view within a scroll view’s visible region when scrolling to a view.

## Declaration

```swift
var scrollTargetAnchor: UnitPoint? { get set }
```

## Discussion

Use this API in conjunction with a `ScrollViewProxy/scrollTo(_:anchor)` or when updating the binding provided to a [scrollPosition(id:anchor:)](../View/scrollPosition_id_anchor.zh-Hans.md).

```swift
@Binding var position: Item.ID?

var body: some View {
    ScrollView {
        LazyVStack {
            ForEach(items) { item in
                ItemView(item)
            }
        }
        .scrollTargetLayout()
    }
    .scrollPosition(id: $position)
    .safeAreaInset(edge: .bottom) {
        Button("Scroll To Bottom") {
            withAnimation {
                withTransaction(\.scrollTargetAnchor, .bottom) {
                    position = items.last?.id
                }
            }
        }
    }
}
```

When used with the [scrollPosition(id:anchor:)](../View/scrollPosition_id_anchor.zh-Hans.md) modifier, this value will be preferred over the anchor specified in the modifier for the current transaction.

## Getting information about a transaction

- **isContinuous**: A Boolean value that indicates whether the transaction originated from an action that produces a sequence of values.
- **tracksVelocity**: Whether this transaction will track the velocity of any animatable properties that change.
- **subscript(_:)**: Accesses the transaction value associated with a custom key.

