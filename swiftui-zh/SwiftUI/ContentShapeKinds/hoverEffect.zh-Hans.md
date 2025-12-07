---
来源： https://developer.apple.com/documentation/SwiftUI/ContentShapeKinds/hoverEffect
抓取时间： 2025-12-03T06:46:36Z
---

# 悬停效果

**类型属性**

悬停效果的类型。

## 声明

```swift
static let hoverEffect: ContentShapeKinds
```

## 讨论

使用这种效果时，只有预览形状会受到影响。要控制用于点击测试和启动效果的形状，请使用 `interaction` 类型。

在 tvOS 上，该类型用于定义应用于可聚焦和可悬停控件的任何悬停效果的形状，例如按钮边框或剪切形状。

该类型不会影响`onHover`修饰符。

## 获取形状种类

- **interaction**：用于命中测试和可访问性的类型。
- **dragPreview**：用于拖放预览。
- **contextMenuPreview**：用于上下文菜单预览的类型。
- **focusEffect**：用于焦点效果的类型。
- **accessibility**：用于无障碍视觉效果和排序。


---
source: https://developer.apple.com/documentation/SwiftUI/ContentShapeKinds/hoverEffect
crawled: 2025-12-03T06:46:36Z
---

# hoverEffect

**Type Property**

The kind for hover effects.

## Declaration

```swift
static let hoverEffect: ContentShapeKinds
```

## Discussion

When using this kind, only the preview shape is affected. To control the shape used to hit-test and start the effect, use the `interaction` kind.

On tvOS, this is used to define the shape of any hover effect applied to focusable and hoverable controls, for example button border or clipping shapes.

This kind does not affect the `onHover` modifier.

## Getting shape kinds

- **interaction**: The kind for hit-testing and accessibility.
- **dragPreview**: The kind for drag and drop previews.
- **contextMenuPreview**: The kind for context menu previews.
- **focusEffect**: The kind for the focus effect.
- **accessibility**: The kind for accessibility visuals and sorting.

