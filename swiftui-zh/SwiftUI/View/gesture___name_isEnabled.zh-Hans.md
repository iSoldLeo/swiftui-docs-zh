--- 来源：https://developer.apple.com/documentation/SwiftUI/View/gesture(_:name:isEnabled:)

抓取时间：2025-12-02T17:40:59Z

---

# gesture(_:name:isEnabled:)

**实例方法**

将手势附加到视图，其优先级低于视图自身定义的手势。

## 声明

```swift
nonisolated func gesture<T>(_ gesture: T, name: String, isEnabled: Bool = true) -> some View where T : Gesture

```

## 参数

- **gesture**：要附加到视图的手势。

- **name**：用于标识手势的字符串。在 iOS 中，该名称可用于设置 UIKit 手势识别器与此手势之间的失败关系。

- **isEnabled**：添加的手势是否已启用。默认值为 `true`。

## 讨论

当需要将手势附加到视图时，请使用此方法。以下示例定义了一个自定义手势，该手势会向控制台打印一条消息，并将其附加到视图的 [VStack](../VStack.zh-Hans.md)。在 [VStack](../VStack.zh-Hans.md) 中，一个红色心形 [Image](../Image.zh-Hans.md) 定义了自己的 [TapGesture](../TapGesture.zh-Hans.md) 处理程序，该处理程序也会向控制台打印一条消息；此外，还有一个蓝色矩形，它没有自定义手势处理程序。点击或单击该图像会从图像上的点击手势处理程序向控制台打印一条消息；而点击或单击 [VStack](../VStack.zh-Hans.md) 内的矩形会从其所在的垂直堆栈手势处理程序向控制台打印一条消息。

您还可以使用 `isEnabled` 参数来有条件地禁用该手势。

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

- **gesture(_:isEnabled:)**：将一个优先级低于视图自身定义的手势的手势附加到视图。

- **gesture(_:including:)**：将一个优先级低于视图自身定义的手势的手势附加到视图。

- **DragGesture**：一个拖动动作，当拖动事件序列发生变化时，该动作会触发相应的操作。

- **WindowDragGesture**：一个识别并处理窗口拖动动作的手势。

- **MagnifyGesture**：一个识别放大动作并跟踪放大倍数的手势。

- **RotateGesture**：一种识别旋转动作并跟踪旋转角度的手势。

- **RotateGesture3D**：一种识别 3D 旋转动作并跟踪旋转角度和轴的手势。

- **GestureMask**：用于控制向视图添加手势如何影响该视图及其子视图识别的其他手势的选项。


---
source: https://developer.apple.com/documentation/SwiftUI/View/gesture(_:name:isEnabled:)
crawled: 2025-12-02T17:40:59Z
---

# gesture(_:name:isEnabled:)

**Instance Method**

Attaches a gesture to the view with a lower precedence than gestures defined by the view.

## Declaration

```swift
nonisolated func gesture<T>(_ gesture: T, name: String, isEnabled: Bool = true) -> some View where T : Gesture

```

## Parameters

- **gesture**: A gesture to attach to the view.
- **name**: A string that identifies the gesture. In iOS, the name can be used to set up failure relationships between UIKit gesture recognizers and this gesture.
- **isEnabled**: Whether the added gesture is enabled. The default value is `true`.

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
- **gesture(_:isEnabled:)**: Attaches a gesture to the view with a lower precedence than gestures defined by the view.
- **gesture(_:including:)**: Attaches a gesture to the view with a lower precedence than gestures defined by the view.
- **DragGesture**: A dragging motion that invokes an action as the drag-event sequence changes.
- **WindowDragGesture**: A gesture that recognizes the motion of and handles dragging a window.
- **MagnifyGesture**: A gesture that recognizes a magnification motion and tracks the amount of magnification.
- **RotateGesture**: A gesture that recognizes a rotation motion and tracks the angle of the rotation.
- **RotateGesture3D**: A gesture that recognizes 3D rotation motion and tracks the angle and axis of the rotation.
- **GestureMask**: Options that control how adding a gesture to a view affects other gestures recognized by the view and its subviews.

