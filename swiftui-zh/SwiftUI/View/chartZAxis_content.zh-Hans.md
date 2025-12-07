--- 来源：https://developer.apple.com/documentation/SwiftUI/View/chartZAxis(content:)

抓取时间：2025-11-30T21:07:56Z

---

# chartZAxis(content:)

**实例方法**

配置视图中 3D 图表的 Z 轴。

## 声明

```swift
nonisolated func chartZAxis<Content>(@AxisContentBuilder content: () -> Content) -> some View where Content : AxisContent

```

## 参数

- **content**：轴的内容。

## 说明

使用此修饰符自定义图表的 Z 轴。提供一个 `AxisMarks` 构建器，该构建器组合 `AxisGridLine`、`AxisTick` 和 `AxisValueLabel` 结构以形成轴。从构建器中省略组件，即可将其从生成的坐标轴中省略。例如，以下代码会向 z 轴添加网格线：

```swift
.chartZAxis {
    AxisMarks {
        AxisGridLine()
    }
}
```

使用诸如 `position:` 或 `values:` 之类的参数来控制其显示的坐标轴值的位置。


---
source: https://developer.apple.com/documentation/SwiftUI/View/chartZAxis(content:)
crawled: 2025-11-30T21:07:56Z
---

# chartZAxis(content:)

**Instance Method**

Configures the z-axis for 3D charts in the view.

## Declaration

```swift
nonisolated func chartZAxis<Content>(@AxisContentBuilder content: () -> Content) -> some View where Content : AxisContent

```

## Parameters

- **content**: The axis content.

## Discussion

Use this modifier to customize the z-axis of a chart. Provide an `AxisMarks` builder that composes `AxisGridLine`, `AxisTick`, and `AxisValueLabel` structures to form the axis. Omit components from the builder to omit them from the resulting axis. For example, the following code adds grid lines to the z-axis:

```swift
.chartZAxis {
    AxisMarks {
        AxisGridLine()
    }
}
```

Use arguments such as `position:` or `values:` to control the placement of the axis values it displays.



