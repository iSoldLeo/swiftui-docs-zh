--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onTapGesture(count:perform:)

抓取时间：2025-11-30T21:25:55Z

---

# onTapGesture(count:perform:)

**实例方法**

当此视图识别到点击手势时，添加要执行的操作。

## 声明

```swift
nonisolated func onTapGesture(count: Int = 1, perform action: @escaping () -> Void) -> some View

```

## 参数

- **count**：触发 `action` 中提供的操作闭包所需的点击次数。默认为 `1`。

- **action**：要执行的操作。

## 讨论

当用户点击或轻触视图或容器 `count` 次时，使用此方法执行指定的 `action` 操作。

在下面的示例中，每当用户点击或轻触视图两次时，心形图像的颜色就会从 `colors` 数组中随机选择一种颜色：

```swift
struct TapGestureExample: View {
    let colors: [Color] = [.gray, .red, .orange, .yellow,
                           .green, .blue, .purple, .pink]
    @State private var fgColor: Color = .gray

    var body: some View {
        Image(systemName: "heart.fill")
            .resizable()
            .frame(width: 200, height: 200)
            .foregroundColor(fgColor)
            .onTapGesture(count: 2) {
                fgColor = colors.randomElement()!
            }
    }
}
```

## 识别轻触手势

- **onTapGesture(count:coordinateSpace:perform:)**：添加一个操作，当此视图识别到轻触手势时执行该操作，并为该操作提供交互位置信息。

- **TapGesture**：识别一次或多次轻触的手势。

- **SpatialTapGesture**：识别一次或多次轻触并报告其位置的手势。


---
source: https://developer.apple.com/documentation/SwiftUI/View/onTapGesture(count:perform:)
crawled: 2025-11-30T21:25:55Z
---

# onTapGesture(count:perform:)

**Instance Method**

Adds an action to perform when this view recognizes a tap gesture.

## Declaration

```swift
nonisolated func onTapGesture(count: Int = 1, perform action: @escaping () -> Void) -> some View

```

## Parameters

- **count**: The number of taps or clicks required to trigger the action closure provided in `action`. Defaults to `1`.
- **action**: The action to perform.

## Discussion

Use this method to perform the specified `action` when the user clicks or taps on the view or container `count` times.



In the example below, the color of the heart images changes to a random color from the `colors` array whenever the user clicks or taps on the view twice:

```swift
struct TapGestureExample: View {
    let colors: [Color] = [.gray, .red, .orange, .yellow,
                           .green, .blue, .purple, .pink]
    @State private var fgColor: Color = .gray

    var body: some View {
        Image(systemName: "heart.fill")
            .resizable()
            .frame(width: 200, height: 200)
            .foregroundColor(fgColor)
            .onTapGesture(count: 2) {
                fgColor = colors.randomElement()!
            }
    }
}
```



## Recognizing tap gestures

- **onTapGesture(count:coordinateSpace:perform:)**: Adds an action to perform when this view recognizes a tap gesture, and provides the action with the location of the interaction.
- **TapGesture**: A gesture that recognizes one or more taps.
- **SpatialTapGesture**: A gesture that recognizes one or more taps and reports their location.

