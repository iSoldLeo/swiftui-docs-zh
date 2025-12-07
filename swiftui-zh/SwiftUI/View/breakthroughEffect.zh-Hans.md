--- 来源：https://developer.apple.com/documentation/SwiftUI/View/breakthroughEffect(_:)

抓取时间：2025-11-30T21:07:40Z

---

#breakthroughEffect(_:)

**实例方法**

确保视图始终对用户可见，即使它被其他内容（例如 3D 模型）遮挡。

## 声明

```swift
nonisolated func breakthroughEffect(_ effect: BreakthroughEffect) -> some View

```

## 参数

- **effect**：当视图被其他内容遮挡时要应用的效果类型。

## 说明

突破效果允许元素即使在其他应用内容（3D 模型、UI 元素）位于其前方时也对用户可见。元素突破前方内容的方式取决于所选的 [BreakthroughEffect](../BreakthroughEffect.zh-Hans.md)。

此修饰符可用于多种场景，包括装饰物和附件，使其完全穿透前方内容。

### 常规元素

要使 SwiftUI 元素穿透前方内容，请将修饰符 `breakthroughEffect` 直接应用于视图：

```swift
ResizeHandle()
    .breakthroughEffect(.subtle)
```

### 装饰物

当应用于装饰物的全部内容时，装饰物（包括其背景）将穿透前方内容：

```swift
Text("A view with an ornament")
    .ornament(attachmentAnchor: .scene(.bottom)) {
        OrnamentContent()
            .glassBackgroundEffect()
            .breakthroughEffect(.prominent)
    }
```

### RealityView 附件

类似地，`RealityView` `Attachment` 可以穿透 RealityView 中的其他实体，包括它所附加的实体：

```swift
Attachment(id: "example") {
    AttachmentContent()
        .breakthroughEffect(.subtle)
}
```

### 展示

大多数系统展示默认带有穿透效果。对于这些情况，您可以通过将 [presentationBreakthroughEffect(_:)](presentationBreakthroughEffect.zh-Hans.md) 修饰符应用于演示文稿的内容来自定义效果类型，如下例所示：

```swift
Button("Show Details") {
    isShowingDetails = true
}
.popover(isPresented: $isShowingDetails) {
    DetailsView()
        .presentationBreakthroughEffect(.prominent)
}
```

这也适用于使用 `RealityKit/PresentationComponent` 的 RealityKit 演示文稿。


---
source: https://developer.apple.com/documentation/SwiftUI/View/breakthroughEffect(_:)
crawled: 2025-11-30T21:07:40Z
---

# breakthroughEffect(_:)

**Instance Method**

Ensures that the view is always visible to the user, even when other content is occluding it, like 3D models.

## Declaration

```swift
nonisolated func breakthroughEffect(_ effect: BreakthroughEffect) -> some View

```

## Parameters

- **effect**: The type of effect to apply when the view is occluded by other content.

## Discussion

Breakthrough is an effect allowing elements to be visible to the user even when other app content (3D models, UI elements) is positioned in front. The way the element breaks through content in front depends on the chosen [BreakthroughEffect](../BreakthroughEffect.zh-Hans.md).

This modifier can be used in a number of scenarios, including ornaments and `RealityView` attachments to have them break through in their entirety.

### Regular Elements

To have SwiftUI element break through content in front, apply the `breakthroughEffect` modifier directly to the View:

```swift
ResizeHandle()
    .breakthroughEffect(.subtle)
```

### Ornaments

When applied to the whole content of an ornament, the ornament (including its background) will break through content in front:

```swift
Text("A view with an ornament")
    .ornament(attachmentAnchor: .scene(.bottom)) {
        OrnamentContent()
            .glassBackgroundEffect()
            .breakthroughEffect(.prominent)
    }
```

### RealityView Attachments

Similarly, a `RealityView` `Attachment` can break through other entities in the RealityView, including the entity it is attached to:

```swift
Attachment(id: "example") {
    AttachmentContent()
        .breakthroughEffect(.subtle)
}
```

### Presentations

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

This also applies to RealityKit presentations using `RealityKit/PresentationComponent`

