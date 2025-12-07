---
来源： https://developer.apple.com/documentation/SwiftUI/Animation/default
抓取时间： 2025-12-03T06:12:04Z
---

# 默认

**类型属性**

默认动画实例。

## 声明

```swift
static let `default`: Animation
```

## 讨论

`default`动画是[spring(response:dampingFraction:blendDuration:)](spring_response_dampingFraction_blendDuration.zh-Hans.md)与：

- `response` 等于 `0.55`
- `dampingFraction` 等于 `1.0`
- `blendDuration` 等于 `0.0`

在 iOS 17、macOS 14、tvOS 17 和 watchOS 10 之前，`default` 动画为[easeInOut](easeInOut.zh-Hans.md)。

如果您没有提供动画，全局函数 [withAnimation(_:_:)](../withAnimation.zh-Hans.md) 会使用默认动画。例如，下面的代码列表显示了一个使用`default` 动画的示例，每次有人单击动画按钮时，文本 "Hello "都会翻转。

```swift
struct ContentView: View {
    @State private var degrees = Double.zero

    var body: some View {
        VStack {
            Spacer()
            Text("Hello")
                .font(.largeTitle)
                .rotation3DEffect(.degrees(degrees), axis: (x: 0, y: 1, z: 0))

            Spacer()
            Button("Animate") {
                withAnimation {
                    degrees = (degrees == .zero) ? 180 : .zero
                }
            }
        }
    }
}
```



要在添加[animation(_:value:)](../View/animation___value.zh-Hans.md) 视图修饰符时使用`default` 动画，请将其明确指定为动画类型。例如，下面的代码显示了一个`default` 动画示例，每次有人单击动画按钮时，文本 "Hello "就会旋转。

```swift
struct ContentView: View {
    @State private var degrees = Double.zero

    var body: some View {
        VStack {
            Spacer()
            Text("Hello")
                .font(.largeTitle)
                .rotationEffect(.degrees(degrees))
                .animation(.default, value: degrees)

            Spacer()
            Button("Animate") {
                degrees = (degrees == .zero) ? 360 : .zero
            }
        }
    }
}
```



一个`default` 动画实例只等于其他`default` 动画实例（使用 `==`），而不等于其他动画实例（即使动画完全相同）。例如，如果使用[spring(response:dampingFraction:blendDuration:)](spring_response_dampingFraction_blendDuration.zh-Hans.md) 修改器创建的动画与`default` 使用的参数值相同，则该动画不等于`default`。通过这种行为，您可以区分有意选择的动画和使用`default` 动画的动画。


---
source: https://developer.apple.com/documentation/SwiftUI/Animation/default
crawled: 2025-12-03T06:12:04Z
---

# default

**Type Property**

A default animation instance.

## Declaration

```swift
static let `default`: Animation
```

## Discussion

The `default` animation is [spring(response:dampingFraction:blendDuration:)](spring_response_dampingFraction_blendDuration.zh-Hans.md) with:

- `response` equal to `0.55`
- `dampingFraction` equal to `1.0`
- `blendDuration` equal to `0.0`

Prior to iOS 17, macOS 14, tvOS 17, and watchOS 10, the `default` animation is [easeInOut](easeInOut.zh-Hans.md).

The global function [withAnimation(_:_:)](../withAnimation.zh-Hans.md) uses the default animation if you don’t provide one. For instance, the following code listing shows an example of using the `default` animation to flip the text “Hello” each time someone clicks the Animate button.

```swift
struct ContentView: View {
    @State private var degrees = Double.zero

    var body: some View {
        VStack {
            Spacer()
            Text("Hello")
                .font(.largeTitle)
                .rotation3DEffect(.degrees(degrees), axis: (x: 0, y: 1, z: 0))

            Spacer()
            Button("Animate") {
                withAnimation {
                    degrees = (degrees == .zero) ? 180 : .zero
                }
            }
        }
    }
}
```



To use the `default` animation when adding the [animation(_:value:)](../View/animation___value.zh-Hans.md) view modifier, specify it explicitly as the animation type. For instance, the following code shows an example of the `default` animation to spin the text “Hello” each time someone clicks the Animate button.

```swift
struct ContentView: View {
    @State private var degrees = Double.zero

    var body: some View {
        VStack {
            Spacer()
            Text("Hello")
                .font(.largeTitle)
                .rotationEffect(.degrees(degrees))
                .animation(.default, value: degrees)

            Spacer()
            Button("Animate") {
                degrees = (degrees == .zero) ? 360 : .zero
            }
        }
    }
}
```



A `default` animation instance is only equal to other `default` animation instances (using `==`), and not equal to other animation instances even when the animations are identical. For example, if you create an animation using the [spring(response:dampingFraction:blendDuration:)](spring_response_dampingFraction_blendDuration.zh-Hans.md) modifier with the same parameter values that `default` uses, the animation isn’t equal to `default`. This behavior lets you differentiate between animations that you intentionally choose and those that use the `default` animation.

