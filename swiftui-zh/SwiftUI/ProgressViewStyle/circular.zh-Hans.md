--- 来源：https://developer.apple.com/documentation/SwiftUI/ProgressViewStyle/circular

抓取时间：2025-12-03T06:10:16Z

---

# circular

**Type 属性**

使用圆形仪表盘指示活动部分完成情况的进度视图样式。

## 声明

```swift
@MainActor @preconcurrency static var circular: CircularProgressViewStyle { get }
```

## 讨论

在 watchOS 以及小组件和复杂功能中，圆形进度视图以 [accessoryCircularCapacity](../GaugeStyle/accessoryCircularCapacity.zh-Hans.md) 样式显示为仪表盘。如果进度视图不确定，则仪表盘为空。

如果没有可用的确定性圆形进度视图样式，则圆形进度视图使用不确定样式。

## 获取内置进度视图样式

- **automatic**：当前视图上下文中的默认进度视图样式。

- **linear**：进度视图，使用水平条直观地显示进度。


---
source: https://developer.apple.com/documentation/SwiftUI/ProgressViewStyle/circular
crawled: 2025-12-03T06:10:16Z
---

# circular

**Type Property**

The style of a progress view that uses a circular gauge to indicate the partial completion of an activity.

## Declaration

```swift
@MainActor @preconcurrency static var circular: CircularProgressViewStyle { get }
```

## Discussion

On watchOS, and in widgets and complications, a circular progress view appears as a gauge with the [accessoryCircularCapacity](../GaugeStyle/accessoryCircularCapacity.zh-Hans.md) style. If the progress view is indeterminate, the gauge is empty.

In cases where no determinate circular progress view style is available, circular progress views use an indeterminate style.

## Getting built-in progress view styles

- **automatic**: The default progress view style in the current context of the view being styled.
- **linear**: A progress view that visually indicates its progress using a horizontal bar.

