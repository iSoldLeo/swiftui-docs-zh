--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onTapGesture(count:coordinateSpace:perform:)

抓取时间：2025-11-30T21:25:56Z

---

# onTapGesture(count:coordinateSpace:perform:)

**实例方法**

当此视图识别到点击手势时，添加一个要执行的操作，并将交互位置提供给该操作。

## 声明

```swift
nonisolated func onTapGesture(count: Int = 1, coordinateSpace: some CoordinateSpaceProtocol = .local, perform action: @escaping (CGPoint) -> Void) -> some View

```

## 参数

- **count**：触发 `action` 中提供的操作闭包所需的点击次数。默认为 `1`。

- **coordinateSpace**：接收位置值的坐标空间。默认值为 [local](../CoordinateSpace/local.zh-Hans.md)。

- **action**：要执行的操作。此闭包接收一个输入，指示交互发生的位置。

## 讨论

当用户在修改后的视图上点击或轻触 `count` 次时，使用此方法执行指定的 `action`。操作闭包接收交互位置。

以下代码向 [Circle](../Circle.zh-Hans.md) 添加一个点击手势，该手势根据点击位置切换圆圈的颜色。

```swift
struct TapGestureExample: View {
    @State private var location: CGPoint = .zero

    var body: some View {
        Circle()
            .fill(self.location.y > 50 ? Color.blue : Color.red)
            .frame(width: 100, height: 100, alignment: .center)
            .onTapGesture { location in
                self.location = location
            }
    }
}
```

## 识别点击手势

- **onTapGesture(count:perform:)**：添加一个操作，当此视图识别到点击手势时执行。

- **TapGesture**：识别一次或多次点击的手势。 - **SpatialTapGesture**：一种手势识别器，能够识别一次或多次点击并报告其位置。


---
source: https://developer.apple.com/documentation/SwiftUI/View/onTapGesture(count:coordinateSpace:perform:)
crawled: 2025-11-30T21:25:56Z
---

# onTapGesture(count:coordinateSpace:perform:)

**Instance Method**

Adds an action to perform when this view recognizes a tap gesture, and provides the action with the location of the interaction.

## Declaration

```swift
nonisolated func onTapGesture(count: Int = 1, coordinateSpace: some CoordinateSpaceProtocol = .local, perform action: @escaping (CGPoint) -> Void) -> some View

```

## Parameters

- **count**: The number of taps or clicks required to trigger the action closure provided in `action`. Defaults to `1`.
- **coordinateSpace**: The coordinate space in which to receive location values. Defaults to [local](../CoordinateSpace/local.zh-Hans.md).
- **action**: The action to perform. This closure receives an input that indicates where the interaction occurred.

## Discussion

Use this method to perform the specified `action` when the user clicks or taps on the modified view `count` times. The action closure receives the location of the interaction.



The following code adds a tap gesture to a [Circle](../Circle.zh-Hans.md) that toggles the color of the circle based on the tap location.

```swift
struct TapGestureExample: View {
    @State private var location: CGPoint = .zero

    var body: some View {
        Circle()
            .fill(self.location.y > 50 ? Color.blue : Color.red)
            .frame(width: 100, height: 100, alignment: .center)
            .onTapGesture { location in
                self.location = location
            }
    }
}
```

## Recognizing tap gestures

- **onTapGesture(count:perform:)**: Adds an action to perform when this view recognizes a tap gesture.
- **TapGesture**: A gesture that recognizes one or more taps.
- **SpatialTapGesture**: A gesture that recognizes one or more taps and reports their location.

