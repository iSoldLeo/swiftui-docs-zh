--- 来源：https://developer.apple.com/documentation/SwiftUI/View/simultaneousGesture(_:including:)

抓取时间：2025-11-30T21:26:18Z

---

# simultaneousGesture(_:including:)

**实例方法**

将手势附加到视图，使其与视图定义的其他手势同时处理。

## 声明

```swift
nonisolated func simultaneousGesture<T>(_ gesture: T, including mask: GestureMask = .all) -> some View where T : Gesture

```

## 参数

- **gesture**：要附加到视图的手势。

- **mask**：一个值，用于控制将此手势添加到视图如何影响视图及其子视图识别的其他手势。默认为 [all](../GestureMask/all.zh-Hans.md)。

## 讨论

当您需要同时定义和处理一个视图特定的手势，并使其与视图的现有手势具有相同的优先级时，请使用此方法。以下示例定义了一个自定义手势，该手势会向控制台打印一条消息，并将其附加到视图的 [VStack](../VStack.zh-Hans.md) 上。在 [VStack](../VStack.zh-Hans.md) 内，有一个红色的心形 [Image](../Image.zh-Hans.md)，它定义了自己的 [TapGesture](../TapGesture.zh-Hans.md) 处理程序，该处理程序也会向控制台打印一条消息，此外还有一个没有自定义手势处理程序的蓝色矩形。

点击或单击“心形”图像会向控制台发送两条消息：一条来自图像的点击手势处理程序，另一条来自附加到其内部垂直堆栈的自定义手势处理程序。点击或轻触蓝色矩形框只会将连接到 [VStack](../VStack.zh-Hans.md) 的点击识别器发送到控制台的一条消息：

```swift
struct SimultaneousGestureExample: View {
    @State private var message = "Message"
    let newGesture = TapGesture().onEnded {
        print("Gesture on VStack.")
    }

    var body: some View {
        VStack(spacing:25) {
            Image(systemName: "heart.fill")
                .resizable()
                .frame(width: 75, height: 75)
                .padding()
                .foregroundColor(.red)
                .onTapGesture {
                    print("Gesture on image.")
                }
            Rectangle()
                .fill(Color.blue)
        }
        .simultaneousGesture(newGesture)
        .frame(width: 200, height: 200)
        .border(Color.purple)
    }
}
```

## 组合手势

- **组合 SwiftUI 手势**：组合手势以创建复杂的交互。

- **simultaneousGesture(_:isEnabled:)**：将手势附加到视图，以便与视图定义的其他手势同时处理。

- **simultaneousGesture(_:name:isEnabled:)**：将手势附加到视图，以便与视图定义的其他手势同时处理。

- **SequenceGesture**：由两个手势组成的序列手势。

- **SimultaneousGesture**：包含两个可以同时执行且互不先后的手势。

- **ExclusiveGesture**：一种由两个手势组成的组合手势，其中只有一个手势能够成功。


---
source: https://developer.apple.com/documentation/SwiftUI/View/simultaneousGesture(_:including:)
crawled: 2025-11-30T21:26:18Z
---

# simultaneousGesture(_:including:)

**Instance Method**

Attaches a gesture to the view to process simultaneously with gestures defined by the view.

## Declaration

```swift
nonisolated func simultaneousGesture<T>(_ gesture: T, including mask: GestureMask = .all) -> some View where T : Gesture

```

## Parameters

- **gesture**: A gesture to attach to the view.
- **mask**: A value that controls how adding this gesture to the view affects other gestures recognized by the view and its subviews. Defaults to [all](../GestureMask/all.zh-Hans.md).

## Discussion

Use this method when you need to define and process  a view specific gesture simultaneously with the same priority as the view’s existing gestures. The example below defines a custom gesture that prints a message to the console and attaches it to the view’s [VStack](../VStack.zh-Hans.md). Inside the [VStack](../VStack.zh-Hans.md) is a red heart [Image](../Image.zh-Hans.md) defines its own [TapGesture](../TapGesture.zh-Hans.md) handler that also prints a message to the console and a blue rectangle with no custom gesture handlers.

Tapping or clicking the “heart” image sends two messages to the console: one for the image’s tap gesture handler, and the other from a custom gesture handler attached to the enclosing vertical stack. Tapping or clicking on the blue rectangle results only in the single message to the console from the tap recognizer attached to the [VStack](../VStack.zh-Hans.md):

```swift
struct SimultaneousGestureExample: View {
    @State private var message = "Message"
    let newGesture = TapGesture().onEnded {
        print("Gesture on VStack.")
    }

    var body: some View {
        VStack(spacing:25) {
            Image(systemName: "heart.fill")
                .resizable()
                .frame(width: 75, height: 75)
                .padding()
                .foregroundColor(.red)
                .onTapGesture {
                    print("Gesture on image.")
                }
            Rectangle()
                .fill(Color.blue)
        }
        .simultaneousGesture(newGesture)
        .frame(width: 200, height: 200)
        .border(Color.purple)
    }
}
```

## Combining gestures

- **Composing SwiftUI gestures**: Combine gestures to create complex interactions.
- **simultaneousGesture(_:isEnabled:)**: Attaches a gesture to the view to process simultaneously with gestures defined by the view.
- **simultaneousGesture(_:name:isEnabled:)**: Attaches a gesture to the view to process simultaneously with gestures defined by the view.
- **SequenceGesture**: A gesture that’s a sequence of two gestures.
- **SimultaneousGesture**: A gesture containing two gestures that can happen at the same time with neither of them preceding the other.
- **ExclusiveGesture**: A gesture that consists of two gestures where only one of them can succeed.

