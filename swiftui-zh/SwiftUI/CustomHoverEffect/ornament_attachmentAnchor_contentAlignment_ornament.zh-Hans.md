--- 来源：https://developer.apple.com/documentation/SwiftUI/CustomHoverEffect/ornament(attachmentAnchor:contentAlignment:ornament:)

抓取时间：2025-12-03T06:45:44Z

---

# ornament(attachmentAnchor:contentAlignment:ornament:)

**类型方法**

鼠标悬停时显示装饰物。

## 声明

```swift
nonisolated static func ornament<Content>(attachmentAnchor: OrnamentAttachmentAnchor, contentAlignment: Alignment3D = .center, @ViewBuilder ornament: () -> Content) -> OrnamentHoverEffect<Content> where Self == OrnamentHoverEffect<Content>, Content : View
```

## 参数

- **attachmentAnchor**：定义装饰物附着点的定位锚点。

- **contentAlignment**：装饰物与其附着锚点的对齐方式。

- **ornament**：装饰物的内容。

## 讨论

使用此方法可在鼠标悬停在视图上时，在指定位置显示装饰物。装饰物将以默认的淡入淡出动画显示。


---
source: https://developer.apple.com/documentation/SwiftUI/CustomHoverEffect/ornament(attachmentAnchor:contentAlignment:ornament:)
crawled: 2025-12-03T06:45:44Z
---

# ornament(attachmentAnchor:contentAlignment:ornament:)

**Type Method**

Presents an ornament on hover.

## Declaration

```swift
nonisolated static func ornament<Content>(attachmentAnchor: OrnamentAttachmentAnchor, contentAlignment: Alignment3D = .center, @ViewBuilder ornament: () -> Content) -> OrnamentHoverEffect<Content> where Self == OrnamentHoverEffect<Content>, Content : View
```

## Parameters

- **attachmentAnchor**: The positioning anchor that defines the attachment point of the ornament.
- **contentAlignment**: The alignment of the ornament with its attachment anchor.
- **ornament**: The content of the ornament.

## Discussion

Use this method to show an ornament at the specified position when the view is hovered. The ornament will be shown with the default fade animation.

