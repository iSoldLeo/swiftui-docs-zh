---
来源： https://developer.apple.com/documentation/SwiftUI/ContentShapeKinds/accessibility
抓取时间： 2025-12-03T06:46:37Z
---

# 无障碍

**类型属性**

无障碍视觉效果和排序的类型。

## 声明

```swift
static let accessibility: ContentShapeKinds
```

## 讨论

使用这种方法设置内容形状会使视图底层辅助元素的辅助框架和路径与该形状相匹配，而无需调整命中测试形状、更新 VoiceOver 等辅助应用程序绘制的视觉焦点环以及元素的排序方式。只有当用于点击测试的形状或大小与视图的视觉形状有明显偏差时，才需要更新辅助功能形状。

要控制无障碍性和命中测试的形状，请使用 `interaction` 类型。

## 获取形状种类

- **interaction**：用于命中测试和可访问性的类型。
- **dragPreview**：用于拖放预览。
- **contextMenuPreview**：用于上下文菜单预览的类型。
- **focusEffect**：用于焦点效果的类型。
- **hoverEffect**：用于悬停效果的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/ContentShapeKinds/accessibility
crawled: 2025-12-03T06:46:37Z
---

# accessibility

**Type Property**

The kind for accessibility visuals and sorting.

## Declaration

```swift
static let accessibility: ContentShapeKinds
```

## Discussion

Setting a content shape with this kind causes the accessibility frame and path of the view’s underlying accessibility element to match the shape without adjusting the hit-testing shape, updating the visual focus ring that assistive apps, such as VoiceOver, draw, as well as how the element is sorted. Updating the accessibility shape is only required if the shape or size used to hit-test significantly diverges from the visual shape of the view.

To control the shape for accessibility and hit-testing, use the `interaction` kind.

## Getting shape kinds

- **interaction**: The kind for hit-testing and accessibility.
- **dragPreview**: The kind for drag and drop previews.
- **contextMenuPreview**: The kind for context menu previews.
- **focusEffect**: The kind for the focus effect.
- **hoverEffect**: The kind for hover effects.

