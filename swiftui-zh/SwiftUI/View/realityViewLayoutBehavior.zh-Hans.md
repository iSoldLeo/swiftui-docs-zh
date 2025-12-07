--- 来源：https://developer.apple.com/documentation/SwiftUI/View/realityViewLayoutBehavior(_:)

抓取时间：2025-11-30T21:10:19Z

---

# realityViewLayoutBehavior(_:)

**实例方法**

一个视图修饰符，用于控制 `RealityView` 的框架大小和内容对齐行为。

## 声明

```swift
@MainActor @preconcurrency func realityViewLayoutBehavior(_ layoutOption: RealityViewLayoutOption) -> some View

```

## 讨论

此修饰符仅在 `make` 闭包结束后生效。在调用 `update` 闭包时不会对其进行检查。

```swift
struct ModelWrapperView: View {
    let modelName: String
    var body: some View {
        RealityView { content in
            let model = try? await Entity(named: modelName)
            if let model {
                content.add(model)
            }
        }
        .realityViewLayoutBehavior(.fixedSize)
    }
}
```

请参阅 `RealityViewLayoutOption`，了解要传递给 `realityViewLayoutBehavior(_:)` 的选项列表。


---
source: https://developer.apple.com/documentation/SwiftUI/View/realityViewLayoutBehavior(_:)
crawled: 2025-11-30T21:10:19Z
---

# realityViewLayoutBehavior(_:)

**Instance Method**

A view modifier that controls the frame sizing and content alignment behavior for `RealityView`

## Declaration

```swift
@MainActor @preconcurrency func realityViewLayoutBehavior(_ layoutOption: RealityViewLayoutOption) -> some View

```

## Discussion

This modifier is only accounted for after the end of the `make` closure. It isn’t checked on any calls to the `update` closure.

```swift
struct ModelWrapperView: View {
    let modelName: String
    var body: some View {
        RealityView { content in
            let model = try? await Entity(named: modelName)
            if let model {
                content.add(model)
            }
        }
        .realityViewLayoutBehavior(.fixedSize)
    }
}
```

See `RealityViewLayoutOption` for a list of options to pass into `realityViewLayoutBehavior(_:)`.

