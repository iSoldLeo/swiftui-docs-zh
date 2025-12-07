---
来源： https://developer.apple.com/documentation/SwiftUI/ScrollIndicatorVisibility
抓取时间： 2025-12-02T17:40:39Z
---

# 滚动指示器可见性

**Structure**

UI 元素的滚动指示符的可见性。

### 声明

```swift
struct ScrollIndicatorVisibility
```

## 概览

向 [scrollIndicators(_:axes:)](View/scrollIndicators___axes.zh-Hans.md) 方法传递该类型的值，以指定视图层次结构的首选滚动条可见性。

## 获取可见性

- **automatic**：滚动条可见性取决于接受可见性配置的组件的策略。
- **hidden**：隐藏滚动条指示符。
- **never**：不应显示滚动指示符。
- **visible**：显示滚动指示符。

## 显示滚动条指示符

- **scrollIndicatorsFlash(onAppear:)**：出现可滚动视图时，闪烁该视图的滚动指示符。
- **scrollIndicatorsFlash(trigger:)**：当数值发生变化时，闪烁可滚动视图的滚动指示符。
- **scrollIndicators(_:axes:)**：设置该视图中滚动指示符的可见性。
- **horizontalScrollIndicatorVisibility**：适用于任何可水平滚动内容的滚动指示符的可见性。
- **verticalScrollIndicatorVisibility**：适用于任何可垂直滚动内容的滚动指示符的可见性。

## 符合

- 可复制
- 等价


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollIndicatorVisibility
crawled: 2025-12-02T17:40:39Z
---

# ScrollIndicatorVisibility

**Structure**

The visibility of scroll indicators of a UI element.

## Declaration

```swift
struct ScrollIndicatorVisibility
```

## Overview

Pass a value of this type to the [scrollIndicators(_:axes:)](View/scrollIndicators___axes.zh-Hans.md) method to specify the preferred scroll indicator visibility of a view hierarchy.

## Getting visibilties

- **automatic**: Scroll indicator visibility depends on the policies of the component accepting the visibility configuration.
- **hidden**: Hide the scroll indicators.
- **never**: Scroll indicators should never be visible.
- **visible**: Show the scroll indicators.

## Showing scroll indicators

- **scrollIndicatorsFlash(onAppear:)**: Flashes the scroll indicators of a scrollable view when it appears.
- **scrollIndicatorsFlash(trigger:)**: Flashes the scroll indicators of scrollable views when a value changes.
- **scrollIndicators(_:axes:)**: Sets the visibility of scroll indicators within this view.
- **horizontalScrollIndicatorVisibility**: The visibility to apply to scroll indicators of any horizontally scrollable content.
- **verticalScrollIndicatorVisibility**: The visiblity to apply to scroll indicators of any vertically scrollable content.

## Conforms To

- Copyable
- Equatable

