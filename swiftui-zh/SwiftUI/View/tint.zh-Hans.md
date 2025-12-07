--- 来源：https://developer.apple.com/documentation/SwiftUI/View/tint(_:)

抓取时间：2025-11-30T21:21:53Z

---

# tint(_:)

**实例方法**

设置此视图的色调。

## 声明

```swift
nonisolated func tint(_ tint: Color?) -> some View

```

## 参数

- **tint**：要应用的色调。

## 说明

使用此方法可以覆盖此视图的默认强调色。与应用程序的强调色（可通过用户偏好进行覆盖）不同，色调始终有效，应将其用作赋予控件额外含义的一种方式。

此示例分别展示了带有 [green](../ShapeStyle/green.zh-Hans.md) 和 [red](../ShapeStyle/red.zh-Hans.md) 色调的“接听”和“拒绝”按钮。

```swift
struct ControlTint: View {
    var body: some View {
        HStack {
            Button {
                // Answer the call
            } label: {
                Label("Answer", systemImage: "phone")
            }
            .tint(.green)
            Button {
                // Decline the call
            } label: {
                Label("Decline", systemImage: "phone.down")
            }
            .tint(.red)
        }
        .buttonStyle(.borderedProminent)
        .padding()
    }
}
```

某些控件会根据其样式、当前平台和上下文以不同的方式调整色调。例如，在 macOS 中，样式为 [bordered](../PrimitiveButtonStyle/bordered.zh-Hans.md) 的按钮不会为其背景着色，而样式为 [borderedProminent](../PrimitiveButtonStyle/borderedProminent.zh-Hans.md) 的按钮则会。在 macOS 中，这两种按钮样式都不会为其标签着色，但在其他平台上会。

## 设置颜色

- **Color**：一种能够适应特定上下文的颜色表示。


---
source: https://developer.apple.com/documentation/SwiftUI/View/tint(_:)
crawled: 2025-11-30T21:21:53Z
---

# tint(_:)

**Instance Method**

Sets the tint color within this view.

## Declaration

```swift
nonisolated func tint(_ tint: Color?) -> some View

```

## Parameters

- **tint**: The tint [Color](../Color.zh-Hans.md) to apply.

## Discussion

Use this method to override the default accent color for this view. Unlike an app’s accent color, which can be overridden by user preference, the tint color is always respected and should be used as a way to provide additional meaning to the control.

This example shows Answer and Decline buttons with [green](../ShapeStyle/green.zh-Hans.md) and [red](../ShapeStyle/red.zh-Hans.md) tint colors, respectively.

```swift
struct ControlTint: View {
    var body: some View {
        HStack {
            Button {
                // Answer the call
            } label: {
                Label("Answer", systemImage: "phone")
            }
            .tint(.green)
            Button {
                // Decline the call
            } label: {
                Label("Decline", systemImage: "phone.down")
            }
            .tint(.red)
        }
        .buttonStyle(.borderedProminent)
        .padding()
    }
}
```

Some controls adapt to the tint color differently based on their style, the current platform, and the surrounding context. For example, in macOS, a button with the [bordered](../PrimitiveButtonStyle/bordered.zh-Hans.md) style doesn’t tint its background, but one with the [borderedProminent](../PrimitiveButtonStyle/borderedProminent.zh-Hans.md) style does. In macOS, neither of these button styles tint their label, but they do in other platforms.

## Setting a color

- **Color**: A representation of a color that adapts to a given context.

