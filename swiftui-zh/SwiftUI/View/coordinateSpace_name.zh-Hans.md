--- 来源：https://developer.apple.com/documentation/SwiftUI/View/coordinateSpace(name:)

抓取时间：2025-12-03T05:35:43Z

---

# coordinateSpace(name:)

**实例方法**

为视图的坐标空间指定一个名称，以便其他代码可以相对于该命名空间操作点和尺寸等维度。

## 声明

```swift
nonisolated func coordinateSpace<T>(name: T) -> some View where T : Hashable

```

## 参数

- **name**：用于标识此坐标空间的名称。

## 说明

使用 `coordinateSpace(name:)` 可以允许其他函数查找并操作视图，并相对于该视图操作维度。

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
        .coordinateSpace(name: "stack")
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

视图`circle`附加了一个[DragGesture](../DragGesture.zh-Hans.md)，该视图指向外层视图VStack的坐标空间。当手势识别器的闭包在 `circle` 内注册事件时，它会将这些事件存储在共享的 `location` 状态变量中，然后 [VStack](../VStack.zh-Hans.md) 会在 [Text](../Text.zh-Hans.md) 视图中显示这些坐标。

## 布局修饰符

- **frame()**：将此视图定位在一个不可见的框架内。

- **edgesIgnoringSafeArea(_:)**：更改视图的建议区域，使其扩展到屏幕安全区域之外。


---
source: https://developer.apple.com/documentation/SwiftUI/View/coordinateSpace(name:)
crawled: 2025-12-03T05:35:43Z
---

# coordinateSpace(name:)

**Instance Method**

Assigns a name to the view’s coordinate space, so other code can operate on dimensions like points and sizes relative to the named space.

## Declaration

```swift
nonisolated func coordinateSpace<T>(name: T) -> some View where T : Hashable

```

## Parameters

- **name**: A name used to identify this coordinate space.

## Discussion

Use `coordinateSpace(name:)` to allow another function to find and operate on a view and operate on dimensions relative to that view.

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
        .coordinateSpace(name: "stack")
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



## Layout modifiers

- **frame()**: Positions this view within an invisible frame.
- **edgesIgnoringSafeArea(_:)**: Changes the view’s proposed area to extend outside the screen’s safe areas.

