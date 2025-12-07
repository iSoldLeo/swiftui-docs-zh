---
来源： https://developer.apple.com/documentation/SwiftUI/Animation/easeOut
抓取时间： 2025-12-03T06:12:07Z
---

# easeOut

**类型属性**

动画开始时速度很快，动作结束时速度减慢。

## 声明

```swift
static var easeOut: Animation { get }
```

## 返回值

默认持续时间的缓和动画。

## 讨论

缓和动画通过改变动画的加速度和减速度，为运动提供自然的感觉，这与现实中事物的运动方式相吻合。在缓和动画中，运动开始时速度很快，到结束时速度逐渐减慢。

`easeOut` 动画的默认持续时间为 0.35 秒。要指定不同的持续时间，请使用 [easeOut(duration:)](easeOut_duration.zh-Hans.md)。

下面的代码举例说明了如何使用渐变动画来改变[Circle](../Circle.zh-Hans.md) 的大小。

```swift
struct ContentView: View {
    @State private var scale = 0.5

    var body: some View {
        VStack {
            Circle()
                .scale(scale)
                .animation(.easeOut, value: scale)
            HStack {
                Button("+") { scale += 0.1 }
                Button("-") { scale -= 0.1 }
            }
        }
    }
}
```



## 获取缓和动画

- **easeIn**：开始时速度较慢，动作结束时速度加快的动画。
- **easeIn(duration:)**：指定持续时间的动画，开始时速度较慢，动作结束时速度加快。
- **easeOut(duration:)**：具有指定持续时间的动画，开始时速度较快，动作结束时速度减慢。
- **easeInOut**：结合了进出缓和动画行为的动画。
- **easeInOut(duration:)**：具有指定持续时间的动画，结合了渐进和渐出动画的行为。


---
source: https://developer.apple.com/documentation/SwiftUI/Animation/easeOut
crawled: 2025-12-03T06:12:07Z
---

# easeOut

**Type Property**

An animation that starts quickly and then slows towards the end of the movement.

## Declaration

```swift
static var easeOut: Animation { get }
```

## Return Value

An ease-out animation with the default duration.

## Discussion

An easing animation provides motion with a natural feel by varying the acceleration and deceleration of the animation, which matches how things tend to move in reality. With an ease out animation, the motion starts quickly and decreases its speed towards the end.

The `easeOut` animation has a default duration of 0.35 seconds. To specify a different duration, use [easeOut(duration:)](easeOut_duration.zh-Hans.md).

The following code shows an example of animating the size changes of a [Circle](../Circle.zh-Hans.md) using an ease out animation.

```swift
struct ContentView: View {
    @State private var scale = 0.5

    var body: some View {
        VStack {
            Circle()
                .scale(scale)
                .animation(.easeOut, value: scale)
            HStack {
                Button("+") { scale += 0.1 }
                Button("-") { scale -= 0.1 }
            }
        }
    }
}
```



## Getting eased animations

- **easeIn**: An animation that starts slowly and then increases speed towards the end of the movement.
- **easeIn(duration:)**: An animation with a specified duration that starts slowly and then increases speed towards the end of the movement.
- **easeOut(duration:)**: An animation with a specified duration that starts quickly and then slows towards the end of the movement.
- **easeInOut**: An animation that combines the behaviors of in and out easing animations.
- **easeInOut(duration:)**: An animation with a specified duration that combines the behaviors of in and out easing animations.

