--- 来源：https://developer.apple.com/documentation/SwiftUI/View/scrollEdgeEffectHidden(_:for:)

抓取时间：2025-11-30T21:10:23Z

---

# scrollEdgeEffectHidden(_:for:)

**实例方法**

隐藏此层级结构中滚动视图的滚动边缘效果。

## 声明

```swift
nonisolated func scrollEdgeEffectHidden(_ hidden: Bool = true, for edges: Edge.Set = .all) -> some View

```

## 说明

默认情况下，滚动视图会渲染自动边缘效果样式。使用此方法可以隐藏此层级结构中滚动视图的滚动边缘效果。

```swift
ScrollView {
    LazyVStack {
        ForEach(data) { item in
            RowView(item)
        }
    }
}
.scrollEdgeEffectHidden()
```

## 配置滚动边缘效果

- **scrollEdgeEffectStyle(_:for:)**：配置此层级结构中滚动视图的滚动边缘效果样式。

- **ScrollEdgeEffectStyle**：定义滚动视图的隐藏区域样式的结构体。

- **safeAreaBar(edge:alignment:spacing:content:)**：在修改后的视图旁边显示自定义栏，其中包含指定的内容。


---
source: https://developer.apple.com/documentation/SwiftUI/View/scrollEdgeEffectHidden(_:for:)
crawled: 2025-11-30T21:10:23Z
---

# scrollEdgeEffectHidden(_:for:)

**Instance Method**

Hides any scroll edge effects for scroll views within this hierarchy.

## Declaration

```swift
nonisolated func scrollEdgeEffectHidden(_ hidden: Bool = true, for edges: Edge.Set = .all) -> some View

```

## Discussion

By default, a scroll view renders an automatic edge effect style. Use this modifier to hide any edge effects for scroll views within this hierarchy.

```swift
ScrollView {
    LazyVStack {
        ForEach(data) { item in
            RowView(item)
        }
    }
}
.scrollEdgeEffectHidden()
```

## Configuring scroll edge effects

- **scrollEdgeEffectStyle(_:for:)**: Configures the scroll edge effect style for scroll views within this hierarchy.
- **ScrollEdgeEffectStyle**: A structure that defines the style of pocket a scroll view will have.
- **safeAreaBar(edge:alignment:spacing:content:)**: Shows the specified content as a custom bar beside the modified view.

