--- 来源：https://developer.apple.com/documentation/SwiftUI/UIHostingOrnament/init(sceneAnchor:contentAlignment:content:)

抓取时间：2025-12-01T11:50:18Z

---

# init(sceneAnchor:contentAlignment:content:)

**Initializer**

创建一个具有指定对齐方式和内容的装饰物。

## 声明

```swift
init(sceneAnchor: UnitPoint, contentAlignment: Alignment = .center, @ViewBuilder content: () -> Content)
```

## 参数

- **sceneAnchor**：用于将装饰物的内容（基于 `contentAlignment`）与场景对齐的锚点。

- **contentAlignment**：用于定位装饰物的对齐方式。

- **content**：装饰物的内容。

## 创建宿主装饰

- **rootView**：此装饰所管理的 SwiftUI 视图层级结构的根视图。


---
source: https://developer.apple.com/documentation/SwiftUI/UIHostingOrnament/init(sceneAnchor:contentAlignment:content:)
crawled: 2025-12-01T11:50:18Z
---

# init(sceneAnchor:contentAlignment:content:)

**Initializer**

Creates an ornament with the specified alignment and content.

## Declaration

```swift
init(sceneAnchor: UnitPoint, contentAlignment: Alignment = .center, @ViewBuilder content: () -> Content)
```

## Parameters

- **sceneAnchor**: The anchor point for aligning the ornament’s content (based on the `contentAlignment`) with the scene.
- **contentAlignment**: The alignment in the ornament used to position it.
- **content**: The content of the ornament.

## Creating a hosting ornament

- **rootView**: The root view of the SwiftUI view hierarchy managed by this ornament.

