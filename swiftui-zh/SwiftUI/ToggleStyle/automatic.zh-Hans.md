---
来源： https://developer.apple.com/documentation/SwiftUI/ToggleStyle/automatic
抓取时间：2025-12-03T06:09:47Z
---

# 自动

**类型属性**

默认的切换样式。

## 声明

```swift
@MainActor @preconcurrency static var automatic: DefaultToggleStyle { get }
```

## 讨论

使用此[ToggleStyle](../ToggleStyle.zh-Hans.md) 可让 SwiftUI 为当前平台和上下文选择合适的样式。切换按钮默认使用 `automatic` 样式，但您可能需要使用 [toggleStyle(_:)](../View/toggleStyle.zh-Hans.md) 修饰符显式设置该样式，以覆盖环境中的其他样式。例如，您可以要求为[HStack](../HStack.zh-Hans.md) 中的切换按钮自动设置样式，而在其他情况下，该切换按钮被配置为使用[button](button.zh-Hans.md) 样式：

```swift
HStack {
    Toggle(isOn: $isShuffling) {
        Label("Shuffle", systemImage: "shuffle")
    }
    Toggle(isOn: $isRepeating) {
        Label("Repeat", systemImage: "repeat")
    }

    Divider()

    Toggle("Enhance Sound", isOn: $isEnhanced)
        .toggleStyle(.automatic) // Set the style automatically here.
}
.toggleStyle(.button) // Use button style for toggles in the stack.
```

### 平台默认值

`automatic`样式产生的外观因平台而异，在大多数情况下使用以下样式：



tvOS 的默认样式类似于按钮。不过，与其他平台上的[switch](switch.zh-Hans.md)样式不同，tvOS 切换按钮占用的水平空间与父级按钮相同，并同时显示切换标签和指示切换状态的文本字段。你通常会把 tvOS 切换按钮集合到一个 [List](../List.zh-Hans.md)中：

```swift
List {
    Toggle("Show Lyrics", isOn: $isShowingLyrics)
    Toggle("Shuffle", isOn: $isShuffling)
    Toggle("Repeat", isOn: $isRepeating)
}
```



### 上下文默认值

在某些情况下，切换开关的自动外观会有所不同：

- 作为您提供给工具栏修饰符之一的内容的一部分出现的切换，如 [toolbar(content:)](../View/toolbar_content.zh-Hans.md)，默认使用[button](button.zh-Hans.md)样式。
- [Menu](../Menu.zh-Hans.md)中的切换使用的样式是无法显式创建的：

```swift
Menu("Playback") {
    Toggle("Show Lyrics", isOn: $isShowingLyrics)
    Toggle("Shuffle", isOn: $isShuffling)
    Toggle("Repeat", isOn: $isRepeating)
}
```

SwiftUI 用复选标记显示切换标签，该复选标记仅在`on` 状态下显示：



## 获取内置的切换样式

- **button**：切换样式，以按钮形式显示，其标签为标题。
- **checkbox**：一种切换样式，显示一个复选框，后面跟有标签。
- **switch**：一种切换样式，显示前面的标签和后面的开关。


---
source: https://developer.apple.com/documentation/SwiftUI/ToggleStyle/automatic
crawled: 2025-12-03T06:09:47Z
---

# automatic

**Type Property**

The default toggle style.

## Declaration

```swift
@MainActor @preconcurrency static var automatic: DefaultToggleStyle { get }
```

## Discussion

Use this [ToggleStyle](../ToggleStyle.zh-Hans.md) to let SwiftUI pick a suitable style for the current platform and context. Toggles use the `automatic` style by default, but you might need to set it explicitly using the [toggleStyle(_:)](../View/toggleStyle.zh-Hans.md) modifier to override another style in the environment. For example, you can request automatic styling for a toggle in an [HStack](../HStack.zh-Hans.md) that’s otherwise configured to use the [button](button.zh-Hans.md) style:

```swift
HStack {
    Toggle(isOn: $isShuffling) {
        Label("Shuffle", systemImage: "shuffle")
    }
    Toggle(isOn: $isRepeating) {
        Label("Repeat", systemImage: "repeat")
    }

    Divider()

    Toggle("Enhance Sound", isOn: $isEnhanced)
        .toggleStyle(.automatic) // Set the style automatically here.
}
.toggleStyle(.button) // Use button style for toggles in the stack.
```

### Platform defaults

The `automatic` style produces an appearance that varies by platform, using the following styles in most contexts:



The default style for tvOS behaves like a button. However, unlike the [switch](switch.zh-Hans.md) style that’s on other platforms, the tvOS toggle takes as much horizontal space as its parent offers, and displays both the toggle’s label and a text field that indicates the toggle’s state. You typically collect tvOS toggles into a [List](../List.zh-Hans.md):

```swift
List {
    Toggle("Show Lyrics", isOn: $isShowingLyrics)
    Toggle("Shuffle", isOn: $isShuffling)
    Toggle("Repeat", isOn: $isRepeating)
}
```



### Contextual defaults

A toggle’s automatic appearance varies in certain contexts:

- A toggle that appears as part of the content that you provide to one of the toolbar modifiers, like [toolbar(content:)](../View/toolbar_content.zh-Hans.md), uses the [button](button.zh-Hans.md) style by default.
- A toggle in a [Menu](../Menu.zh-Hans.md) uses a style that you can’t create explicitly:

```swift
Menu("Playback") {
    Toggle("Show Lyrics", isOn: $isShowingLyrics)
    Toggle("Shuffle", isOn: $isShuffling)
    Toggle("Repeat", isOn: $isRepeating)
}
```

SwiftUI shows the toggle’s label with a checkmark that appears only in the `on` state:



## Getting built-in toggle styles

- **button**: A toggle style that displays as a button with its label as the title.
- **checkbox**: A toggle style that displays a checkbox followed by its label.
- **switch**: A toggle style that displays a leading label and a trailing switch.

