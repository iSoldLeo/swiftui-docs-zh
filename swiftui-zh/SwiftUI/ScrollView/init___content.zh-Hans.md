---
来源： https://developer.apple.com/documentation/SwiftUI/ScrollView/init(_:content:)
抓取时间： 2025-12-01T10:34:03Z
---

# init(_:content:)

**Initializer**

创建一个新实例，该实例可沿给定轴向滚动，并可在滚动时显示指示符。

### 声明

```swift
nonisolated init(_ axes: Axis.Set = .vertical, @ViewBuilder content: () -> Content)
```

## 参数

- **axes**：滚动视图的滚动轴。默认为垂直轴。
- **content**：创建滚动视图的视图创建器。

## 创建滚动视图

- **init(_:showsIndicators:content:)**：创建一个新实例，该实例可沿给定轴线方向滚动，并可在滚动时显示指示符。


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollView/init(_:content:)
crawled: 2025-12-01T10:34:03Z
---

# init(_:content:)

**Initializer**

Creates a new instance that’s scrollable in the direction of the given axis and can show indicators while scrolling.

## Declaration

```swift
nonisolated init(_ axes: Axis.Set = .vertical, @ViewBuilder content: () -> Content)
```

## Parameters

- **axes**: The scroll view’s scrollable axis. The default axis is the vertical axis.
- **content**: The view builder that creates the scrollable view.

## Creating a scroll view

- **init(_:showsIndicators:content:)**: Creates a new instance that’s scrollable in the direction of the given axis and can show indicators while scrolling.

