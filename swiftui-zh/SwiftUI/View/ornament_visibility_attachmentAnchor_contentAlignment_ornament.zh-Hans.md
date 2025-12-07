--- 来源：https://developer.apple.com/documentation/SwiftUI/View/ornament(visibility:attachmentAnchor:contentAlignment:ornament:)

抓取时间：2025-11-30T20:06:45Z

---

# ornament(visibility:attachmentAnchor:contentAlignment:ornament:)

**实例方法**

显示一个装饰物。

## 声明

```swift
nonisolated func ornament<Content>(visibility: Visibility = .automatic, attachmentAnchor: OrnamentAttachmentAnchor, contentAlignment: Alignment = .center, @ViewBuilder ornament: () -> Content) -> some View where Content : View

```

## 参数

- **visibility**：装饰物的可见性。

- **attachmentAnchor**：定义装饰物连接点的定位锚点。

- **contentAlignment**：装饰物与其连接锚点的对齐方式。

## 说明

使用此方法可在指定位置显示装饰物。以下示例显示了窗口下方的装饰物：

```swift
Text("A view with an ornament")
    .ornament(attachmentAnchor: .scene(.bottom)) {
        OrnamentContent()
    }
```

## 创建装饰物

- **OrnamentAttachmentAnchor**：装饰物的连接锚点。


---
source: https://developer.apple.com/documentation/SwiftUI/View/ornament(visibility:attachmentAnchor:contentAlignment:ornament:)
crawled: 2025-11-30T20:06:45Z
---

# ornament(visibility:attachmentAnchor:contentAlignment:ornament:)

**Instance Method**

Presents an ornament.

## Declaration

```swift
nonisolated func ornament<Content>(visibility: Visibility = .automatic, attachmentAnchor: OrnamentAttachmentAnchor, contentAlignment: Alignment = .center, @ViewBuilder ornament: () -> Content) -> some View where Content : View

```

## Parameters

- **visibility**: The visibility of the ornament.
- **attachmentAnchor**: The positioning anchor that defines the attachment point of the ornament.
- **contentAlignment**: The alignment of the ornament with its attachment anchor.

## Discussion

Use this method to show an ornament at the specified position. The example below displays an ornament below the window:

```swift
Text("A view with an ornament")
    .ornament(attachmentAnchor: .scene(.bottom)) {
        OrnamentContent()
    }
```

## Creating an ornament

- **OrnamentAttachmentAnchor**: An attachment anchor for an ornament.

