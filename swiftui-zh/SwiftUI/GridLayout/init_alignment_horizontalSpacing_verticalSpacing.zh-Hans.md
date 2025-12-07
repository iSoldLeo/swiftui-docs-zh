--- 来源：https://developer.apple.com/documentation/SwiftUI/GridLayout/init(alignment:horizontalSpacing:verticalSpacing:)

抓取时间：2025-12-03T06:39:40Z

---

# init(alignment:horizontalSpacing:verticalSpacing:)

**Initializer**

创建具有指定间距和对齐方式的网格。

## 声明

```swift
init(alignment: Alignment = .center, horizontalSpacing: CGFloat? = nil, verticalSpacing: CGFloat? = nil)
```

## 参数

- **alignment**：用于在给定单元格分配的空间内对齐子视图的参考线。默认值为 [center](../Alignment/center.zh-Hans.md)。

- **horizontalSpacing**：每个单元格之间的水平距离，以磅为单位。默认值为`nil`，表示适用于该平台的默认单元格间距。

- **verticalSpacing**：表示每个单元格之间的垂直距离，单位为磅。默认值为`nil`，表示适用于该平台的默认单元格间距。


---
source: https://developer.apple.com/documentation/SwiftUI/GridLayout/init(alignment:horizontalSpacing:verticalSpacing:)
crawled: 2025-12-03T06:39:40Z
---

# init(alignment:horizontalSpacing:verticalSpacing:)

**Initializer**

Creates a grid with the specified spacing and alignment.

## Declaration

```swift
init(alignment: Alignment = .center, horizontalSpacing: CGFloat? = nil, verticalSpacing: CGFloat? = nil)
```

## Parameters

- **alignment**: The guide for aligning subviews within the space allocated for a given cell. The default is [center](../Alignment/center.zh-Hans.md).
- **horizontalSpacing**: The horizontal distance between each cell, given in points. The value is `nil` by default, which results in a default distance between cells that’s appropriate for the platform.
- **verticalSpacing**: The vertical distance between each cell, given in points. The value is `nil` by default, which results in a default distance between cells that’s appropriate for the platform.

