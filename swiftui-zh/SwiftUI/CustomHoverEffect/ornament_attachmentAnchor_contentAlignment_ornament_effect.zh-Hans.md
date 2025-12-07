--- 来源：https://developer.apple.com/documentation/SwiftUI/CustomHoverEffect/ornament(attachmentAnchor:contentAlignment:ornament:effect:)

抓取时间：2025-12-01T11:34:55Z

---

# ornament(attachmentAnchor:contentAlignment:ornament:effect:)

**类型方法**

鼠标悬停时显示装饰物。

## 声明

```swift
nonisolated static func ornament<Content, EffectContent>(attachmentAnchor: OrnamentAttachmentAnchor, contentAlignment: Alignment3D = .center, @ViewBuilder ornament: () -> Content, effect: @escaping (EmptyHoverEffectContent, Bool, GeometryProxy) -> EffectContent) -> OrnamentHoverContentEffect<Content, EffectContent> where Self == OrnamentHoverContentEffect<Content, EffectContent>, Content : View, EffectContent : HoverEffectContent
```

## 参数

- **attachmentAnchor**：定义装饰物附着点的定位锚点。

- **contentAlignment**：装饰物与其附着锚点的对齐方式。

- **ornament**：装饰物的内容。

- **effect**：用于显示装饰物的效果。

## 说明

使用此方法可在鼠标悬停于视图时，在指定位置显示装饰物。装饰物将使用提供的 `effect` 显示。


---
source: https://developer.apple.com/documentation/SwiftUI/CustomHoverEffect/ornament(attachmentAnchor:contentAlignment:ornament:effect:)
crawled: 2025-12-01T11:34:55Z
---

# ornament(attachmentAnchor:contentAlignment:ornament:effect:)

**Type Method**

Presents an ornament on hover.

## Declaration

```swift
nonisolated static func ornament<Content, EffectContent>(attachmentAnchor: OrnamentAttachmentAnchor, contentAlignment: Alignment3D = .center, @ViewBuilder ornament: () -> Content, effect: @escaping (EmptyHoverEffectContent, Bool, GeometryProxy) -> EffectContent) -> OrnamentHoverContentEffect<Content, EffectContent> where Self == OrnamentHoverContentEffect<Content, EffectContent>, Content : View, EffectContent : HoverEffectContent
```

## Parameters

- **attachmentAnchor**: The positioning anchor that defines the attachment point of the ornament.
- **contentAlignment**: The alignment of the ornament with its attachment anchor.
- **ornament**: The content of the ornament.
- **effect**: The effect used to present the ornament.

## Discussion

Use this method to present an ornament at the specified position when the view is hovered. The ornament will be presented using the provided `effect`.

