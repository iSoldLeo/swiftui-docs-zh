--- 来源：https://developer.apple.com/documentation/SwiftUI/View/coordinateSpace(_:)

抓取时间：2025-12-02T17:37:43Z

---

# coordinateSpace(_:)

**实例方法**

为视图的坐标空间指定一个名称，以便其他代码可以相对于该命名空间操作点和尺寸等维度。

## 声明

```swift
nonisolated func coordinateSpace(_ name: NamedCoordinateSpace) -> some View

```

## 参数

- **name**：用于标识此坐标空间的名称。

## 说明

使用 `coordinateSpace(_:)` 可以允许其他函数查找并操作视图，并相对于该视图操作维度。

以下示例演示了嵌套视图如何查找并操作其外层视图的坐标空间：

```swift
struct ContentView: View {
    @State private var location = CGPoint.zero

    var body: some View {
        VStack {
            Color.red.frame(width: 100, height: 100)
                .overlay(circle)
            Text("Location: \(Int(location.x)), \(Int(location.y))")
        }
        .coordinateSpace(.named("stack"))
    }

    var circle: some View {
        Circle()
            .frame(width: 25, height: 25)
            .gesture(drag)
            .padding(5)
    }

    var drag: some Gesture {
        DragGesture(coordinateSpace: .named("stack"))
            .onChanged { info in location = info.location }
    }
}
```

此处，名为“stack”的`ContentView`中的[VStack](../VStack.zh-Hans.md)由一个红色框架组成，框架中心是一个自定义视图[Circle](../Circle.zh-Hans.md)[overlay(_:alignment:)](overlay___alignment.zh-Hans.md)。

视图`circle`附加了一个[DragGesture](../DragGesture.zh-Hans.md)，该视图指向外层视图VStack的坐标空间。当手势识别器的闭包在 `circle` 中注册事件时，它会将这些事件存储在共享的 `location` 状态变量中，而 [VStack](../VStack.zh-Hans.md) 则在 [Text](../Text.zh-Hans.md) 视图中显示这些坐标。

## 测量视图

- **GeometryReader**：一个容器视图，其内容根据自身的大小和坐标空间进行定义。

- **GeometryReader3D**：一个容器视图，其内容根据自身的大小和坐标空间进行定义。

- **GeometryProxy**：用于访问容器视图的大小和坐标空间（用于锚点解析）的代理。

- **GeometryProxy3D**：用于访问容器视图的大小和坐标空间的代理。

- **CoordinateSpace**：由坐标空间协议创建的已解析坐标空间。

- **CoordinateSpaceProtocol**：布局系统内的参考系。

- **PhysicalMetric**：提供对与指定物理测量值对应的点值的访问。

- **PhysicalMetricsConverter**：物理度量转换器，提供点值与其在三维空间中的范围（以物理长度测量值的形式）之间的转换。


---
source: https://developer.apple.com/documentation/SwiftUI/View/coordinateSpace(_:)
crawled: 2025-12-02T17:37:43Z
---

# coordinateSpace(_:)

**Instance Method**

Assigns a name to the view’s coordinate space, so other code can operate on dimensions like points and sizes relative to the named space.

## Declaration

```swift
nonisolated func coordinateSpace(_ name: NamedCoordinateSpace) -> some View

```

## Parameters

- **name**: A name used to identify this coordinate space.

## Discussion

Use `coordinateSpace(_:)` to allow another function to find and operate on a view and operate on dimensions relative to that view.

The example below demonstrates how a nested view can find and operate on its enclosing view’s coordinate space:

```swift
struct ContentView: View {
    @State private var location = CGPoint.zero

    var body: some View {
        VStack {
            Color.red.frame(width: 100, height: 100)
                .overlay(circle)
            Text("Location: \(Int(location.x)), \(Int(location.y))")
        }
        .coordinateSpace(.named("stack"))
    }

    var circle: some View {
        Circle()
            .frame(width: 25, height: 25)
            .gesture(drag)
            .padding(5)
    }

    var drag: some Gesture {
        DragGesture(coordinateSpace: .named("stack"))
            .onChanged { info in location = info.location }
    }
}
```

Here, the [VStack](../VStack.zh-Hans.md) in the `ContentView` named “stack” is composed of a red frame with a custom [Circle](../Circle.zh-Hans.md) view [overlay(_:alignment:)](overlay___alignment.zh-Hans.md) at its center.

The `circle` view has an attached [DragGesture](../DragGesture.zh-Hans.md) that targets the enclosing VStack’s coordinate space. As the gesture recognizer’s closure registers events inside `circle` it stores them in the shared `location` state variable and the [VStack](../VStack.zh-Hans.md) displays the coordinates in a [Text](../Text.zh-Hans.md) view.



## Measuring a view

- **GeometryReader**: A container view that defines its content as a function of its own size and coordinate space.
- **GeometryReader3D**: A container view that defines its content as a function of its own size and coordinate space.
- **GeometryProxy**: A proxy for access to the size and coordinate space (for anchor resolution) of the container view.
- **GeometryProxy3D**: A proxy for access to the size and coordinate space of the container view.
- **CoordinateSpace**: A resolved coordinate space created by the coordinate space protocol.
- **CoordinateSpaceProtocol**: A frame of reference within the layout system.
- **PhysicalMetric**: Provides access to a value in points that corresponds to the specified physical measurement.
- **PhysicalMetricsConverter**: A physical metrics converter provides conversion between point values and their extent in 3D space, in the form of physical length measurements.

