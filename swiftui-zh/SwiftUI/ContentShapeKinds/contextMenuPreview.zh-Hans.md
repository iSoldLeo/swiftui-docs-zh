---
来源： https://developer.apple.com/documentation/SwiftUI/ContentShapeKinds/contextMenuPreview
抓取时间： 2025-12-03T06:46:34Z
---

# 上下文菜单预览

**类型属性**

上下文菜单预览的类型。

## 声明

```swift
static let contextMenuPreview: ContentShapeKinds
```

## 讨论

使用这种方法时，只有预览形状会受到影响。要控制用于点击测试和启动上下文菜单显示的形状，请使用 `.interaction` 类型。

## 获取形状种类

- **interaction**：用于命中测试和可访问性的类型。
- **dragPreview**：用于拖放预览。
- **focusEffect**：用于聚焦效果的类型。
- **hoverEffect**：用于悬停效果的类型。
- **accessibility**：用于无障碍视觉效果和排序。


---
source: https://developer.apple.com/documentation/SwiftUI/ContentShapeKinds/contextMenuPreview
crawled: 2025-12-03T06:46:34Z
---

# contextMenuPreview

**Type Property**

The kind for context menu previews.

## Declaration

```swift
static let contextMenuPreview: ContentShapeKinds
```

## Discussion

When using this kind, only the preview shape will be affected. To control the shape used to hit-test and start the context menu presentation, use the `.interaction` kind.

## Getting shape kinds

- **interaction**: The kind for hit-testing and accessibility.
- **dragPreview**: The kind for drag and drop previews.
- **focusEffect**: The kind for the focus effect.
- **hoverEffect**: The kind for hover effects.
- **accessibility**: The kind for accessibility visuals and sorting.

