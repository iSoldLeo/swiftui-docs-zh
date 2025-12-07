--- 来源：https://developer.apple.com/documentation/SwiftUI/View/gesture(_:isEnabled:)

抓取时间：2025-11-30T21:26:05Z

---

# gesture(_:isEnabled:)

**实例方法**

将手势附加到视图，其优先级低于视图自身定义的手势。

## 声明

```swift
nonisolated func gesture<T>(_ gesture: T, isEnabled: Bool) -> some View where T : Gesture

```

## 参数

- **gesture**：要附加到视图的手势。

- **isEnabled**：添加的手势是否已启用。

## 说明

当需要将手势附加到视图时，请使用此方法。以下示例定义了一个自定义手势，该手势会将一条消息打印到控制台，并将其附加到视图的 [VStack](../VStack.zh-Hans.md)。在 [VStack](../VStack.zh-Hans.md) 内部，一个红色心形 [Image](../Image.zh-Hans.md) 定义了自己的 [TapGesture](../TapGesture.zh-Hans.md) 处理程序，该处理程序还会向控制台打印一条消息；此外，还有一个没有自定义手势处理程序的蓝色矩形。点击或单击该图像会根据图像上的点击手势处理程序向控制台打印一条消息；而点击或单击 [VStack](../VStack.zh-Hans.md) 内部的矩形则会根据其所在的垂直堆栈手势处理程序向控制台打印一条消息。

您还可以使用 `isEnabled` 参数来有条件地禁用手势。

```swift
struct GestureExample: View {
    @State private var message = "Message"
    var isGestureEnabled: Bool
    let newGesture = TapGesture().onEnded {
        print("Tap on VStack.")
    }

    var body: some View {
        VStack(spacing:25) {
            Image(systemName: "heart.fill")
                .resizable()
                .frame(width: 75, height: 75)
                .padding()
                .foregroundColor(.red)
                .onTapGesture {
                    print("Tap on image.")
                }
            Rectangle()
                .fill(Color.blue)
        }
        .gesture(newGesture, isEnabled: isGestureEnabled)
        .frame(width: 200, height: 200)
        .border(Color.purple)
    }
}
```

## 识别随时间变化的手势

- **gesture(_:)**：将 [NSGestureRecognizerRepresentable](../NSGestureRecognizerRepresentable.zh-Hans.md) 附加到视图。

- **gesture(_:name:isEnabled:)**：将一个手势附加到视图，其优先级低于视图自身定义的手势。

- **gesture(_:including:)**：将一个手势附加到视图，其优先级低于视图自身定义的手势。

- **DragGesture**：拖动动作，当拖动事件序列发生变化时触发相应的操作。

- **WindowDragGesture**：识别并处理窗口拖动动作的手势。

- **MagnifyGesture**：识别放大动作并跟踪放大倍数的手势。

- **RotateGesture**：识别旋转动作并跟踪旋转角度的手势。

- **RotateGesture3D**：一种识别 3D 旋转运动并跟踪旋转角度和轴的手势。

- **GestureMask**：用于控制向视图添加手势如何影响该视图及其子视图识别的其他手势的选项。


---
source: https://developer.apple.com/documentation/SwiftUI/View/gesture(_:isEnabled:)
crawled: 2025-11-30T21:26:05Z
---

# gesture(_:isEnabled:)

**Instance Method**

Attaches a gesture to the view with a lower precedence than gestures defined by the view.

## Declaration

```swift
nonisolated func gesture<T>(_ gesture: T, isEnabled: Bool) -> some View where T : Gesture

```

## Parameters

- **gesture**: A gesture to attach to the view.
- **isEnabled**: Whether the added gesture is enabled.

## Discussion

Use this method when you need to attach a gesture to a view. The example below defines a custom gesture that prints a message to the console and attaches it to the view’s [VStack](../VStack.zh-Hans.md). Inside the [VStack](../VStack.zh-Hans.md) a red heart [Image](../Image.zh-Hans.md) defines its own [TapGesture](../TapGesture.zh-Hans.md) handler that also prints a message to the console, and blue rectangle with no custom gesture handlers. Tapping or clicking the image prints a message to the console from the tap gesture handler on the image, while tapping or clicking  the rectangle inside the [VStack](../VStack.zh-Hans.md) prints a message in the console from the enclosing vertical stack gesture handler.

You can also use the `isEnabled` parameter to conditionally disable the gesture.

```swift
struct GestureExample: View {
    @State private var message = "Message"
    var isGestureEnabled: Bool
    let newGesture = TapGesture().onEnded {
        print("Tap on VStack.")
    }

    var body: some View {
        VStack(spacing:25) {
            Image(systemName: "heart.fill")
                .resizable()
                .frame(width: 75, height: 75)
                .padding()
                .foregroundColor(.red)
                .onTapGesture {
                    print("Tap on image.")
                }
            Rectangle()
                .fill(Color.blue)
        }
        .gesture(newGesture, isEnabled: isGestureEnabled)
        .frame(width: 200, height: 200)
        .border(Color.purple)
    }
}
```

## Recognizing gestures that change over time

- **gesture(_:)**: Attaches an [NSGestureRecognizerRepresentable](../NSGestureRecognizerRepresentable.zh-Hans.md) to the view.
- **gesture(_:name:isEnabled:)**: Attaches a gesture to the view with a lower precedence than gestures defined by the view.
- **gesture(_:including:)**: Attaches a gesture to the view with a lower precedence than gestures defined by the view.
- **DragGesture**: A dragging motion that invokes an action as the drag-event sequence changes.
- **WindowDragGesture**: A gesture that recognizes the motion of and handles dragging a window.
- **MagnifyGesture**: A gesture that recognizes a magnification motion and tracks the amount of magnification.
- **RotateGesture**: A gesture that recognizes a rotation motion and tracks the angle of the rotation.
- **RotateGesture3D**: A gesture that recognizes 3D rotation motion and tracks the angle and axis of the rotation.
- **GestureMask**: Options that control how adding a gesture to a view affects other gestures recognized by the view and its subviews.

