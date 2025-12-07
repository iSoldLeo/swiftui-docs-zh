--- 来源：https://developer.apple.com/documentation/SwiftUI/View/presentationBreakthroughEffect(_:)

抓取时间：2025-11-30T21:10:15Z

---

# presentationBreakthroughEffect(_:)

**实例方法**

更改外层演示元素穿透遮挡内容的方式。

## 声明

```swift
nonisolated func presentationBreakthroughEffect(_ effect: BreakthroughEffect) -> some View

```

## 参数

- **effect**：当演示元素被其他内容遮挡时要应用的效果类型。

## 说明

使用此修饰符可以禁用或自定义外层演示元素的穿透效果。

穿透效果允许元素即使在被其他应用内容（例如 3D 模型、UI 元素）遮挡时也能对用户可见。元素的显示方式取决于所选的 [BreakthroughEffect](../BreakthroughEffect.zh-Hans.md)。

大多数系统演示默认带有突破效果。对于这些情况，您可以通过将 [presentationBreakthroughEffect(_:)](presentationBreakthroughEffect.zh-Hans.md) 修饰符应用于演示内容来自定义效果类型，如下例所示：

```swift
Button("Show Details") {
    isShowingDetails = true
}
.popover(isPresented: $isShowingDetails) {
    DetailsView()
        .presentationBreakthroughEffect(.prominent)
}
```

只有弹出框允许完全禁用突破效果。为工作表传递 `.none` 值无效。


---
source: https://developer.apple.com/documentation/SwiftUI/View/presentationBreakthroughEffect(_:)
crawled: 2025-11-30T21:10:15Z
---

# presentationBreakthroughEffect(_:)

**Instance Method**

Changes the way the enclosing presentation breaks through content occluding it.

## Declaration

```swift
nonisolated func presentationBreakthroughEffect(_ effect: BreakthroughEffect) -> some View

```

## Parameters

- **effect**: The type of effect to apply when a presentation element is occluded by other content.

## Discussion

Use this modifier to disable or customize a breakthrough effect for the enclosing presentation.

Breakthrough is an effect allowing elements to be visible to the user even when other app content (3D models, UI elements) is occluding it. The way the element appears depends on the chosen [BreakthroughEffect](../BreakthroughEffect.zh-Hans.md).

Most system presentations appear with a breakthrough effect by default. For these cases, you can customize the type of effect by applying the [presentationBreakthroughEffect(_:)](presentationBreakthroughEffect.zh-Hans.md) modifier to the content of the presentation, like in the following example:

```swift
Button("Show Details") {
    isShowingDetails = true
}
.popover(isPresented: $isShowingDetails) {
    DetailsView()
        .presentationBreakthroughEffect(.prominent)
}
```

Only popovers allow breakthrough to be disabled altogether. Passing a `.none` value for a sheet has no effect.

