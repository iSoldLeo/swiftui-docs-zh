---
来源：https://developer.apple.com/documentation/SwiftUI/Animation/easeIn(持续时间：)
抓取时间： 2025-12-03T06:12:07Z
---

# easeIn(duration:)

**类型方法**

指定持续时间的动画，开始时速度较慢，动作结束时速度加快。

## 声明

```swift
static func easeIn(duration: TimeInterval) -> Animation
```

## 参数

- **duration**：动画完成所需的时间长度（以秒为单位）。

## 返回值

指定持续时间的缓入动画。

## 讨论

缓进动画通过改变动画的加速度和减速度，为运动提供自然的感觉，这与现实中事物的运动方式相吻合。在缓入动画中，运动开始时速度较慢，到结束时速度逐渐加快。

如果要指定动画完成所需的时间，请使用 `easeIn(duration:)`。否则，请使用 [easeIn](easeIn.zh-Hans.md) 在默认时间内执行动画。

下面的代码举例说明了如何使用持续时间为一秒的轻松动画来改变[Circle](../Circle.zh-Hans.md) 的大小。

```swift
struct ContentView: View {
    @State private var scale = 0.5

    var body: some View {
        VStack {
            Circle()
                .scale(scale)
                .animation(.easeIn(duration: 1.0), value: scale)
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
- **easeOut**：开始时速度很快，动作结束时速度减慢的动画。
- **easeOut(duration:)**：具有指定持续时间的动画，该动画快速启动，然后在动作结束时变慢。
- **easeInOut**：结合了进出缓和动画行为的动画。
- **easeInOut(duration:)**：具有指定持续时间的动画，结合了渐进和渐出动画的行为。


---
source: https://developer.apple.com/documentation/SwiftUI/Animation/easeIn(duration:)
crawled: 2025-12-03T06:12:07Z
---

# easeIn(duration:)

**Type Method**

An animation with a specified duration that starts slowly and then increases speed towards the end of the movement.

## Declaration

```swift
static func easeIn(duration: TimeInterval) -> Animation
```

## Parameters

- **duration**: The length of time, expressed in seconds, that the animation takes to complete.

## Return Value

An ease-in animation with a specified duration.

## Discussion

An easing animation provides motion with a natural feel by varying the acceleration and deceleration of the animation, which matches how things tend to move in reality. With an ease in animation, the motion starts slowly and increases its speed towards the end.

Use `easeIn(duration:)` when you want to specify the time it takes for the animation to complete. Otherwise, use [easeIn](easeIn.zh-Hans.md) to perform the animation for a default length of time.

The following code shows an example of animating the size changes of a [Circle](../Circle.zh-Hans.md) using an ease in animation with a duration of one second.

```swift
struct ContentView: View {
    @State private var scale = 0.5

    var body: some View {
        VStack {
            Circle()
                .scale(scale)
                .animation(.easeIn(duration: 1.0), value: scale)
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
- **easeOut**: An animation that starts quickly and then slows towards the end of the movement.
- **easeOut(duration:)**: An animation with a specified duration that starts quickly and then slows towards the end of the movement.
- **easeInOut**: An animation that combines the behaviors of in and out easing animations.
- **easeInOut(duration:)**: An animation with a specified duration that combines the behaviors of in and out easing animations.

