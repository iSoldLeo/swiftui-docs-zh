--- 来源：https://developer.apple.com/documentation/SwiftUI/View/scrollDismissesKeyboard(_:)

抓取时间：2025-11-30T21:20:24Z

---

# scrollDismissesKeyboard(_:)

**实例方法**

配置可滚动内容与软件键盘交互的行为。

## 声明

```swift
nonisolated func scrollDismissesKeyboard(_ mode: ScrollDismissesKeyboardMode) -> some View

```

## 参数

- **mode**：可滚动内容使用的键盘关闭模式。

## 返回值

使用指定键盘关闭模式的视图。

## 说明

您可以使用此修饰符自定义可滚动内容与软件键盘的交互方式。例如，您可以指定值 [immediately](../ScrollDismissesKeyboardMode/immediately.zh-Hans.md)，表示您希望在开始滚动拖动手势时，如果键盘存在，则可滚动内容立即关闭键盘。 ```swift
@State private var text = ""

ScrollView {
    TextField("Prompt", text: $text)
    ForEach(0 ..< 50) { index in
        Text("\(index)")
            .padding()
    }
}
.scrollDismissesKeyboard(.immediately)
```

您还可以使用此修饰符自定义其他类型可滚动视图（例如 [List](../List.zh-Hans.md) 或 [TextEditor](../TextEditor.zh-Hans.md)）的键盘关闭行为。

默认情况下，[TextEditor](../TextEditor.zh-Hans.md) 是交互式的，而其他类型的可滚动内容在链接到 iOS 16 或更高版本时，滚动时键盘始终关闭。传递值 [never](../ScrollDismissesKeyboardMode/never.zh-Hans.md) 表示可滚动内容不应自动关闭键盘。

## 与软件键盘交互

- **scrollDismissesKeyboardMode**：可滚动内容与软件键盘交互的方式。

- **ScrollDismissesKeyboardMode**：可滚动内容可以与软件键盘交互的方式。


---
source: https://developer.apple.com/documentation/SwiftUI/View/scrollDismissesKeyboard(_:)
crawled: 2025-11-30T21:20:24Z
---

# scrollDismissesKeyboard(_:)

**Instance Method**

Configures the behavior in which scrollable content interacts with the software keyboard.

## Declaration

```swift
nonisolated func scrollDismissesKeyboard(_ mode: ScrollDismissesKeyboardMode) -> some View

```

## Parameters

- **mode**: The keyboard dismissal mode that scrollable content uses.

## Return Value

A view that uses the specified keyboard dismissal mode.

## Discussion

You use this modifier to customize how scrollable content interacts with the software keyboard. For example, you can specify a value of [immediately](../ScrollDismissesKeyboardMode/immediately.zh-Hans.md) to indicate that you would like scrollable content to immediately dismiss the keyboard if present when a scroll drag gesture begins.

```swift
@State private var text = ""

ScrollView {
    TextField("Prompt", text: $text)
    ForEach(0 ..< 50) { index in
        Text("\(index)")
            .padding()
    }
}
.scrollDismissesKeyboard(.immediately)
```

You can also use this modifier to customize the keyboard dismissal behavior for other kinds of scrollable views, like a [List](../List.zh-Hans.md) or a [TextEditor](../TextEditor.zh-Hans.md).

By default, a [TextEditor](../TextEditor.zh-Hans.md) is interactive while other kinds of scrollable content always dismiss the keyboard on a scroll when linked against iOS 16 or later. Pass a value of [never](../ScrollDismissesKeyboardMode/never.zh-Hans.md) to indicate that scrollable content should never automatically dismiss the keyboard.

## Interacting with a software keyboard

- **scrollDismissesKeyboardMode**: The way that scrollable content interacts with the software keyboard.
- **ScrollDismissesKeyboardMode**: The ways that scrollable content can interact with the software keyboard.

