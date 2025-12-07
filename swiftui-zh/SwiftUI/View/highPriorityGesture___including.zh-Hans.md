--- 来源：https://developer.apple.com/documentation/SwiftUI/View/highPriorityGesture(_:including:)

抓取时间：2025-11-30T21:26:21Z

---

# highPriorityGesture(_:including:)

**实例方法**

将一个手势附加到视图，其优先级高于视图自身定义的手势。

## 声明

```swift
nonisolated func highPriorityGesture<T>(_ gesture: T, including mask: GestureMask = .all) -> some View where T : Gesture

```

## 参数

- **gesture**：要附加到视图的手势。

- **mask**：一个值，用于控制将此手势添加到视图如何影响视图及其子视图识别的其他手势。默认为 [all](../GestureMask/all.zh-Hans.md)。

## 讨论

当您需要定义一个高优先级手势，使其优先级高于视图中已有的手势时，请使用此方法。以下示例定义了一个自定义手势，该手势会向控制台打印一条消息，并将其附加到视图的 [VStack](../VStack.zh-Hans.md) 元素。在 [VStack](../VStack.zh-Hans.md) 元素内，一个红色心形 [Image](../Image.zh-Hans.md) 元素定义了自己的 [TapGesture](../TapGesture.zh-Hans.md) 处理程序，该处理程序也会向控制台打印一条消息；此外，还有一个蓝色矩形元素，该元素没有自定义手势处理程序。点击或单击任何视图都会导致从附加到其外层 [VStack](../VStack.zh-Hans.md) 元素的高优先级手势中向控制台发送一条消息。

```swift
struct HighPriorityGestureExample: View {
    @State private var message = "Message"
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
        .highPriorityGesture(newGesture)
        .frame(width: 200, height: 200)
        .border(Color.purple)
    }
}
```

## 定义自定义手势

- **highPriorityGesture(_:isEnabled:)**：将一个手势附加到视图，其优先级高于视图定义的手势。

- **highPriorityGesture(_:name:isEnabled:)**：将手势附加到视图，使其优先级高于视图定义的手势。

- **handGestureShortcut(_:isEnabled:)**：为修改后的控件分配手势快捷键。

- **defersSystemGestures(on:)**：设置手势优先于系统手势的屏幕边缘。

- **Gesture**：将事件序列与手势匹配，并返回其每个状态的值流的实例。

- **AnyGesture**：擦除输入的手势。

- **HandActivationBehavior**：特定于手部输入的激活行为。

- **HandGestureShortcut**：手势快捷键描述用户可以通过手指和手腕的动作来激活按钮或切换开关。


---
source: https://developer.apple.com/documentation/SwiftUI/View/highPriorityGesture(_:including:)
crawled: 2025-11-30T21:26:21Z
---

# highPriorityGesture(_:including:)

**Instance Method**

Attaches a gesture to the view with a higher precedence than gestures defined by the view.

## Declaration

```swift
nonisolated func highPriorityGesture<T>(_ gesture: T, including mask: GestureMask = .all) -> some View where T : Gesture

```

## Parameters

- **gesture**: A gesture to attach to the view.
- **mask**: A value that controls how adding this gesture to the view affects other gestures recognized by the view and its subviews. Defaults to [all](../GestureMask/all.zh-Hans.md).

## Discussion

Use this method when you need to define a high priority gesture to take precedence over the view’s existing gestures. The example below defines a custom gesture that prints a message to the console and attaches it to the view’s [VStack](../VStack.zh-Hans.md). Inside the [VStack](../VStack.zh-Hans.md) a red heart [Image](../Image.zh-Hans.md) defines its own [TapGesture](../TapGesture.zh-Hans.md) handler that also prints a message to the console, and a blue rectangle with no custom gesture handlers. Tapping or clicking any of the views results in a console message from the high priority gesture attached to the enclosing [VStack](../VStack.zh-Hans.md).

```swift
struct HighPriorityGestureExample: View {
    @State private var message = "Message"
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
        .highPriorityGesture(newGesture)
        .frame(width: 200, height: 200)
        .border(Color.purple)
    }
}
```

## Defining custom gestures

- **highPriorityGesture(_:isEnabled:)**: Attaches a gesture to the view with a higher precedence than gestures defined by the view.
- **highPriorityGesture(_:name:isEnabled:)**: Attaches a gesture to the view with a higher precedence than gestures defined by the view.
- **handGestureShortcut(_:isEnabled:)**: Assigns a hand gesture shortcut to the modified control.
- **defersSystemGestures(on:)**: Sets the screen edge from which you want your gesture to take precedence over the system gesture.
- **Gesture**: An instance that matches a sequence of events to a gesture, and returns a stream of values for each of its states.
- **AnyGesture**: A type-erased gesture.
- **HandActivationBehavior**: An activation behavior specific to hand-driven input.
- **HandGestureShortcut**: Hand gesture shortcuts describe finger and wrist movements that the user can perform in order to activate a button or toggle.

