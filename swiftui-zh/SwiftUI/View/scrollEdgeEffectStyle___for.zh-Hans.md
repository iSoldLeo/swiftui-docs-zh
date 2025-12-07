--- 来源：https://developer.apple.com/documentation/SwiftUI/View/scrollEdgeEffectStyle(_:for:)

抓取时间：2025-11-30T21:10:24Z

---

# scrollEdgeEffectStyle(_:for:)

**实例方法**

配置此层级结构中滚动视图的滚动边缘效果样式。

## 声明

```swift
nonisolated func scrollEdgeEffectStyle(_ style: ScrollEdgeEffectStyle?, for edges: Edge.Set) -> some View

```

## 说明

默认情况下，滚动视图会渲染自动边缘效果。使用此修饰符可以更改滚动边缘效果样式。

```swift
ScrollView {
    LazyVStack {
        ForEach(data) { item in
            RowView(item)
        }
    }
}
.scrollEdgeEffectStyle(.hard, for: .all)
```

## 配置滚动边缘效果

- **scrollEdgeEffectHidden(_:for:)**：隐藏此层级结构中滚动视图的所有滚动边缘效果。

- **ScrollEdgeEffectStyle**：定义滚动视图的凹槽样式的结构体。 - **safeAreaBar(edge:alignment:spacing:content:)**：在修改后的视图旁边显示指定内容作为自定义栏。


---
source: https://developer.apple.com/documentation/SwiftUI/View/scrollEdgeEffectStyle(_:for:)
crawled: 2025-11-30T21:10:24Z
---

# scrollEdgeEffectStyle(_:for:)

**Instance Method**

Configures the scroll edge effect style for scroll views within this hierarchy.

## Declaration

```swift
nonisolated func scrollEdgeEffectStyle(_ style: ScrollEdgeEffectStyle?, for edges: Edge.Set) -> some View

```

## Discussion

By default, a scroll view renders an automatic edge effect. Use this modifier to change the scroll edge effect style.

```swift
ScrollView {
    LazyVStack {
        ForEach(data) { item in
            RowView(item)
        }
    }
}
.scrollEdgeEffectStyle(.hard, for: .all)
```

## Configuring scroll edge effects

- **scrollEdgeEffectHidden(_:for:)**: Hides any scroll edge effects for scroll views within this hierarchy.
- **ScrollEdgeEffectStyle**: A structure that defines the style of pocket a scroll view will have.
- **safeAreaBar(edge:alignment:spacing:content:)**: Shows the specified content as a custom bar beside the modified view.

