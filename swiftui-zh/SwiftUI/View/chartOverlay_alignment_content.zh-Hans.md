--- 来源：https://developer.apple.com/documentation/SwiftUI/View/chartOverlay(alignment:content:)

抓取时间：2025-12-01T10:23:06Z

---

# chartOverlay(alignment:content:)

**实例方法**

为包含图表的视图添加一个覆盖层。

## 声明

```swift
nonisolated func chartOverlay<V>(alignment: Alignment = .center, @ViewBuilder content: @escaping (ChartProxy) -> V) -> some View where V : View

```

## 参数

- **alignment**：内容的对齐方式。

- **content**：覆盖层的内容。

## 说明

您可以使用此修饰符将覆盖层视图定义为视图中图表的函数。您可以使用传递给闭包的 `ChartProxy` 对象访问图表。

下面的示例展示了如何定义一个用于处理拖拽手势的叠加视图，并使用代理将手势坐标转换为图表中的数据值。

```swift
Chart(data) {
    LineMark(
        x: .value("date", $0.date),
        y: .value("price", $0.price)
    )
}
.chartOverlay { proxy in
    GeometryReader { geometry in
        Rectangle().fill(.clear).contentShape(Rectangle())
            .gesture(
                DragGesture()
                    .onChanged { value in
                        // Convert the gesture location to the coordinate space of the plot area.
                        let origin = geometry[proxy.plotAreaFrame].origin
                        let location = CGPoint(
                            x: value.location.x - origin.x,
                            y: value.location.y - origin.y
                        )
                        // Get the x (date) and y (price) value from the location.
                        let (date, price) = proxy.value(at: location, as: (Date, Double).self)
                        print("Location: \(date), \(price)")
                    }
            )
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/View/chartOverlay(alignment:content:)
crawled: 2025-12-01T10:23:06Z
---

# chartOverlay(alignment:content:)

**Instance Method**

Adds an overlay to a view that contains a chart.

## Declaration

```swift
nonisolated func chartOverlay<V>(alignment: Alignment = .center, @ViewBuilder content: @escaping (ChartProxy) -> V) -> some View where V : View

```

## Parameters

- **alignment**: The alignment of the content.
- **content**: The content of the overlay.

## Discussion

You can use this modifier to define an overlay view as a function of the chart in the view. You can access the chart with the `ChartProxy` object passed into the closure.

Below is an example where we define an overlay view that handles drag gestures and use the proxy to convert the gesture coordinates to data values in the chart.

```swift
Chart(data) {
    LineMark(
        x: .value("date", $0.date),
        y: .value("price", $0.price)
    )
}
.chartOverlay { proxy in
    GeometryReader { geometry in
        Rectangle().fill(.clear).contentShape(Rectangle())
            .gesture(
                DragGesture()
                    .onChanged { value in
                        // Convert the gesture location to the coordinate space of the plot area.
                        let origin = geometry[proxy.plotAreaFrame].origin
                        let location = CGPoint(
                            x: value.location.x - origin.x,
                            y: value.location.y - origin.y
                        )
                        // Get the x (date) and y (price) value from the location.
                        let (date, price) = proxy.value(at: location, as: (Date, Double).self)
                        print("Location: \(date), \(price)")
                    }
            )
    }
}
```



