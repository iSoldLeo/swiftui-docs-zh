---
来源： https://developer.apple.com/documentation/SwiftUI/Animation/speed(_:)
抓取时间： 2025-12-01T11:01:32Z
---

# speed(_:)

**实例方法**

通过调整速度来改变动画的持续时间。

## 声明

```swift
func speed(_ speed: Double) -> Animation
```

## 参数

- **speed**：SwiftUI 执行动画的速度。

## 返回值

已调整速度的动画。

## 讨论

设置动画的速度会改变动画的持续时间，改变系数为 `speed`。速度值越高，持续时间越短，动画序列越快。例如，速度为 `2.0` 的一秒动画只需一半时间（半秒）即可完成。

```swift
struct ContentView: View {
    @State private var adjustBy = 100.0

    private var oneSecondAnimation: Animation {
       .easeInOut(duration: 1.0)
    }

    var body: some View {
        VStack(spacing: 40) {
            HStack(alignment: .bottom) {
                Capsule()
                    .frame(width: 50, height: 175 - adjustBy)
                Capsule()
                    .frame(width: 50, height: 175 + adjustBy)
            }
            .animation(oneSecondAnimation.speed(2.0), value: adjustBy)

            Button("Animate") {
                adjustBy *= -1
            }
        }
    }
}
```



将`speed` 设置为较小的数值，可以减慢动画的速度，延长动画的持续时间。例如，速度为 `0.25` 的一秒动画需要四秒才能完成。

```swift
struct ContentView: View {
    @State private var adjustBy = 100.0

    private var oneSecondAnimation: Animation {
       .easeInOut(duration: 1.0)
    }

    var body: some View {
        VStack(spacing: 40) {
            HStack(alignment: .bottom) {
                Capsule()
                    .frame(width: 50, height: 175 - adjustBy)
                Capsule()
                    .frame(width: 50, height: 175 + adjustBy)
            }
            .animation(oneSecondAnimation.speed(0.25), value: adjustBy)

            Button("Animate") {
                adjustBy *= -1
            }
        }
    }
}
```



## 配置动画

- **delay(_:)**：将动画的开始时间延迟指定的秒数。
- **repeatCount(_:autoreverses:)**：重复播放指定次数的动画。
- **repeatForever(autoreverses:)**：在包含动画的视图的生命周期内重复动画。


---
source: https://developer.apple.com/documentation/SwiftUI/Animation/speed(_:)
crawled: 2025-12-01T11:01:32Z
---

# speed(_:)

**Instance Method**

Changes the duration of an animation by adjusting its speed.

## Declaration

```swift
func speed(_ speed: Double) -> Animation
```

## Parameters

- **speed**: The speed at which SwiftUI performs the animation.

## Return Value

An animation with the adjusted speed.

## Discussion

Setting the speed of an animation changes the duration of the animation by a factor of `speed`. A higher speed value causes a faster animation sequence due to a shorter duration. For example, a one-second animation with a speed of `2.0` completes in half the time (half a second).

```swift
struct ContentView: View {
    @State private var adjustBy = 100.0

    private var oneSecondAnimation: Animation {
       .easeInOut(duration: 1.0)
    }

    var body: some View {
        VStack(spacing: 40) {
            HStack(alignment: .bottom) {
                Capsule()
                    .frame(width: 50, height: 175 - adjustBy)
                Capsule()
                    .frame(width: 50, height: 175 + adjustBy)
            }
            .animation(oneSecondAnimation.speed(2.0), value: adjustBy)

            Button("Animate") {
                adjustBy *= -1
            }
        }
    }
}
```



Setting `speed` to a lower number slows the animation, extending its duration. For example, a one-second animation with a speed of `0.25` takes four seconds to complete.

```swift
struct ContentView: View {
    @State private var adjustBy = 100.0

    private var oneSecondAnimation: Animation {
       .easeInOut(duration: 1.0)
    }

    var body: some View {
        VStack(spacing: 40) {
            HStack(alignment: .bottom) {
                Capsule()
                    .frame(width: 50, height: 175 - adjustBy)
                Capsule()
                    .frame(width: 50, height: 175 + adjustBy)
            }
            .animation(oneSecondAnimation.speed(0.25), value: adjustBy)

            Button("Animate") {
                adjustBy *= -1
            }
        }
    }
}
```



## Configuring an animation

- **delay(_:)**: Delays the start of the animation by the specified number of seconds.
- **repeatCount(_:autoreverses:)**: Repeats the animation for a specific number of times.
- **repeatForever(autoreverses:)**: Repeats the animation for the lifespan of the view containing the animation.

