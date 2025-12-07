---
来源： https://developer.apple.com/documentation/SwiftUI/Animation/delay(_:)
抓取时间： 2025-12-03T06:12:23Z
---

# delay(_:)

**实例方法**

将动画的开始时间延迟指定的秒数。

## 声明

```swift
func delay(_ delay: TimeInterval) -> Animation
```

## 参数

- **delay**：延迟动画开始的秒数。

## 返回值

延迟启动的动画。

## 讨论

使用此方法可以延迟动画的开始时间。例如，下面的代码是两个胶囊高度变化的动画。第一个[Capsule](../Capsule.zh-Hans.md) 的动画立即开始。但第二个胶囊的动画要到半秒后才开始。

```swift
struct ContentView: View {
    @State private var adjustBy = 100.0

    var body: some View {
        VStack(spacing: 40) {
            HStack(alignment: .bottom) {
                Capsule()
                    .frame(width: 50, height: 175 - adjustBy)
                    .animation(.easeInOut, value: adjustBy)
                Capsule()
                    .frame(width: 50, height: 175 + adjustBy)
                    .animation(.easeInOut.delay(0.5), value: adjustBy)
            }

            Button("Animate") {
                adjustBy *= -1
            }
        }
    }
}
```



## 配置动画

- **repeatCount(_:autoreverses:)**：重复动画特定次数。
- **repeatForever(autoreverses:)**：在包含动画的视图的生命周期内重复动画。
- **speed(_:)**：通过调整速度改变动画的持续时间。


---
source: https://developer.apple.com/documentation/SwiftUI/Animation/delay(_:)
crawled: 2025-12-03T06:12:23Z
---

# delay(_:)

**Instance Method**

Delays the start of the animation by the specified number of seconds.

## Declaration

```swift
func delay(_ delay: TimeInterval) -> Animation
```

## Parameters

- **delay**: The number of seconds to delay the start of the animation.

## Return Value

An animation with a delayed start.

## Discussion

Use this method to delay the start of an animation. For example, the following code animates the height change of two capsules. Animation of the first [Capsule](../Capsule.zh-Hans.md) begins immediately. However, animation of the second one doesn’t begin until a half second later.

```swift
struct ContentView: View {
    @State private var adjustBy = 100.0

    var body: some View {
        VStack(spacing: 40) {
            HStack(alignment: .bottom) {
                Capsule()
                    .frame(width: 50, height: 175 - adjustBy)
                    .animation(.easeInOut, value: adjustBy)
                Capsule()
                    .frame(width: 50, height: 175 + adjustBy)
                    .animation(.easeInOut.delay(0.5), value: adjustBy)
            }

            Button("Animate") {
                adjustBy *= -1
            }
        }
    }
}
```



## Configuring an animation

- **repeatCount(_:autoreverses:)**: Repeats the animation for a specific number of times.
- **repeatForever(autoreverses:)**: Repeats the animation for the lifespan of the view containing the animation.
- **speed(_:)**: Changes the duration of an animation by adjusting its speed.

