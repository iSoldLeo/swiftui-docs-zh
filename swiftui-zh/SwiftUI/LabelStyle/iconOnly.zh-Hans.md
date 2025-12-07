---
来源： https://developer.apple.com/documentation/SwiftUI/LabelStyle/iconOnly
抓取时间： 2025-12-03T06:10:24Z
---

# 仅图标

**类型属性**

只显示标签图标的标签样式。

## 声明

```swift
@MainActor @preconcurrency static var iconOnly: IconOnlyLabelStyle { get }
```

## 讨论

标签标题仍用于非视觉描述，如 VoiceOver。

## 获取内置标签样式

- **automatic**：根据当前上下文自动调整外观的标签样式。
- **titleAndIcon**：使用系统标准布局同时显示标签标题和图标的标签样式。
- **titleOnly**：只显示标签标题的标签样式。


---
source: https://developer.apple.com/documentation/SwiftUI/LabelStyle/iconOnly
crawled: 2025-12-03T06:10:24Z
---

# iconOnly

**Type Property**

A label style that only displays the icon of the label.

## Declaration

```swift
@MainActor @preconcurrency static var iconOnly: IconOnlyLabelStyle { get }
```

## Discussion

The title of the label is still used for non-visual descriptions, such as VoiceOver.

## Getting built-in label styles

- **automatic**: A label style that resolves its appearance automatically based on the current context.
- **titleAndIcon**: A label style that shows both the title and icon of the label using a system-standard layout.
- **titleOnly**: A label style that only displays the title of the label.

