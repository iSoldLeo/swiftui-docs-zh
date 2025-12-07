--- 来源：https://developer.apple.com/documentation/SwiftUI/ScrollEdgeEffectStyle
抓取时间：2025-12-02T17:40:46Z

---

# ScrollEdgeEffectStyle

**Structure**

定义滚动视图边缘样式的结构体。

## 声明

```swift
struct ScrollEdgeEffectStyle
```

## 类型属性

- **automatic**：自动滚动边缘样式。

- **hard**：具有硬切线和分割线的滚动边缘效果。

- **soft**：具有柔和边缘的滚动边缘效果。

## 配置滚动边缘效果

- **scrollEdgeEffectStyle(_:for:)**：配置此层级结构中滚动视图的滚动边缘效果样式。

- **scrollEdgeEffectHidden(_:for:)**：隐藏此层级结构中滚动视图的所有滚动边缘效果。

- **safeAreaBar(edge:alignment:spacing:content:)**：在修改后的视图旁边显示指定内容作为自定义栏。

## 符合以下标准

- Equatable

- Hashable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollEdgeEffectStyle
crawled: 2025-12-02T17:40:46Z
---

# ScrollEdgeEffectStyle

**Structure**

A structure that defines the style of pocket a scroll view will have.

## Declaration

```swift
struct ScrollEdgeEffectStyle
```

## Type Properties

- **automatic**: The automatic scroll pocket style.
- **hard**: A scroll edge effect with a hard cutoff and dividing line.
- **soft**: A scroll edge effect with a soft edge.

## Configuring scroll edge effects

- **scrollEdgeEffectStyle(_:for:)**: Configures the scroll edge effect style for scroll views within this hierarchy.
- **scrollEdgeEffectHidden(_:for:)**: Hides any scroll edge effects for scroll views within this hierarchy.
- **safeAreaBar(edge:alignment:spacing:content:)**: Shows the specified content as a custom bar beside the modified view.

## Conforms To

- Equatable
- Hashable
- Sendable
- SendableMetatype

