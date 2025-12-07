--- 来源：https://developer.apple.com/documentation/SwiftUI/View/accentColor(_:)

抓取时间：2025-12-01T10:24:52Z

---

# accentColor(_:)

**实例方法**

设置此视图及其包含的视图的强调色。

## 声明

```swift
nonisolated func accentColor(_ accentColor: Color?) -> some View

```

## 参数

- **accentColor**：用作强调色的颜色。将值设置为 `nil` 可使用继承的强调色。

## 说明

当您想要为应用程序的用户界面应用一个通用的主题颜色时，请使用 `accentColor(_:)`。某些控件样式会将强调色用作默认的色调颜色。

在下面的示例中，外部视图 [VStack](../VStack.zh-Hans.md) 包含两个子视图。第一个是按钮，使用默认强调色。第二个是 [VStack](../VStack.zh-Hans.md)，其中包含一个按钮和一个滑块，这两个按钮和滑块都采用了其父视图的紫色强调色。请注意，用作 `Slider` 旁边标签的 [Text](../Text.zh-Hans.md) 元素保留了其默认颜色。

```swift
VStack(spacing: 20) {
    Button(action: {}) {
        Text("Regular Button")
    }
    VStack {
        Button(action: {}) {
            Text("Accented Button")
        }
        HStack {
            Text("Accented Slider")
            Slider(value: $sliderValue, in: -100...100, step: 0.1)
        }
    }
    .accentColor(.purple)
}
```

## 图形和渲染修改器

- **mask(_:)**：使用给定视图的 Alpha 通道遮罩此视图。

- **animation(_:)**：将给定的动画应用于此视图中所有可动画的值。

- **cornerRadius(_:antialiased:)**：以指定的圆角半径将此视图裁剪到其边界框。


---
source: https://developer.apple.com/documentation/SwiftUI/View/accentColor(_:)
crawled: 2025-12-01T10:24:52Z
---

# accentColor(_:)

**Instance Method**

Sets the accent color for this view and the views it contains.

## Declaration

```swift
nonisolated func accentColor(_ accentColor: Color?) -> some View

```

## Parameters

- **accentColor**: The color to use as an accent color. Set the value to `nil` to use the inherited accent color.

## Discussion

Use `accentColor(_:)` when you want to apply a broad theme color to your app’s user interface. Some styles of controls use the accent color as a default tint color.



In the example below, the outer [VStack](../VStack.zh-Hans.md) contains two child views. The first is a button with the default accent color. The second is a [VStack](../VStack.zh-Hans.md) that contains a button and a slider, both of which adopt the purple accent color of their containing view. Note that the [Text](../Text.zh-Hans.md) element used as a label alongside the `Slider` retains its default color.

```swift
VStack(spacing: 20) {
    Button(action: {}) {
        Text("Regular Button")
    }
    VStack {
        Button(action: {}) {
            Text("Accented Button")
        }
        HStack {
            Text("Accented Slider")
            Slider(value: $sliderValue, in: -100...100, step: 0.1)
        }
    }
    .accentColor(.purple)
}
```



## Graphics and rendering modifiers

- **mask(_:)**: Masks this view using the alpha channel of the given view.
- **animation(_:)**: Applies the given animation to all animatable values within this view.
- **cornerRadius(_:antialiased:)**: Clips this view to its bounding frame, with the specified corner radius.

