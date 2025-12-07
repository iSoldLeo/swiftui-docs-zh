---
来源：https://developer.apple.com/documentation/SwiftUI/ScrollView/init(_:showsIndicators:content:)
抓取时间： 2025-12-03T05:44:52Z
---

# init(_:showsIndicators:content:)

**Initializer**

创建一个新实例，该实例可沿给定轴的方向滚动，并可在滚动时显示指示符。

### 声明

```swift
init(_ axes: Axis.Set = .vertical, showsIndicators: Bool = true, @ViewBuilder content: () -> Content)
```

## 参数

- **axes**：滚动视图的滚动轴。默认为垂直轴。
- **showsIndicators**：布尔值，表示滚动视图是否以适合平台的方式显示内容偏移的可滚动部分。该参数的默认值为 `true`。
- **content**：创建可滚动视图的视图生成器。

## 创建滚动视图

- **init(_:content:)**：创建一个新实例，该实例可沿给定轴线方向滚动，并可在滚动时显示指示符。


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollView/init(_:showsIndicators:content:)
crawled: 2025-12-03T05:44:52Z
---

# init(_:showsIndicators:content:)

**Initializer**

Creates a new instance that’s scrollable in the direction of the given axis and can show indicators while scrolling.

## Declaration

```swift
init(_ axes: Axis.Set = .vertical, showsIndicators: Bool = true, @ViewBuilder content: () -> Content)
```

## Parameters

- **axes**: The scroll view’s scrollable axis. The default axis is the vertical axis.
- **showsIndicators**: A Boolean value that indicates whether the scroll view displays the scrollable component of the content offset, in a way suitable for the platform. The default value for this parameter is `true`.
- **content**: The view builder that creates the scrollable view.

## Creating a scroll view

- **init(_:content:)**: Creates a new instance that’s scrollable in the direction of the given axis and can show indicators while scrolling.

