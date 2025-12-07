---
来源： https://developer.apple.com/documentation/SwiftUI/ContentShapeKinds/dragPreview
抓取时间： 2025-12-03T06:46:33Z
---

# 拖动预览

**类型属性**

拖放预览的类型。

## 声明

```swift
static let dragPreview: ContentShapeKinds
```

## 讨论

使用此类型时，只有预览形状会受到影响。要控制用于点击测试和启动拖动预览的形状，请使用 `interaction` 类型。

## 获取形状类型

- **interaction**：用于命中测试和可访问性的类型。
- **contextMenuPreview**：用于上下文菜单预览的类型。
- **focusEffect**：用于焦点效果的类型。
- **hoverEffect**：用于悬停效果的类型。
- **accessibility**：用于无障碍视觉效果和排序。


---
source: https://developer.apple.com/documentation/SwiftUI/ContentShapeKinds/dragPreview
crawled: 2025-12-03T06:46:33Z
---

# dragPreview

**Type Property**

The kind for drag and drop previews.

## Declaration

```swift
static let dragPreview: ContentShapeKinds
```

## Discussion

When using this kind, only the preview shape is affected. To control the shape used to hit-test and start the drag preview, use the `interaction` kind.

## Getting shape kinds

- **interaction**: The kind for hit-testing and accessibility.
- **contextMenuPreview**: The kind for context menu previews.
- **focusEffect**: The kind for the focus effect.
- **hoverEffect**: The kind for hover effects.
- **accessibility**: The kind for accessibility visuals and sorting.

