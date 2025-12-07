---
来源： https://developer.apple.com/documentation/SwiftUI/Animation/easeInOut
抓取时间： 2025-12-03T06:12:09Z
---

# easeInOut

**类型属性**

一种结合 "入 "和 "出 "缓和动画行为的动画。

## 声明

```swift
static var easeInOut: Animation { get }
```

## 返回值

默认持续时间的缓入缓出动画。

## 讨论

缓进缓出动画通过改变动画的加速度和减速度，为运动提供自然的感觉，这与现实中事物的运动方式相吻合。缓入缓出动画开始时速度较慢，到中途时速度逐渐加快，最后在动画结束时速度逐渐减慢。

`easeInOut` 动画的默认持续时间为 0.35 秒。要指定持续时间，请使用 [easeInOut(duration:)](easeInOut_duration.zh-Hans.md) 方法。

下面的代码举例说明了如何使用易入易出动画改变[Circle](../Circle.zh-Hans.md) 的大小。

```swift
struct ContentView: View {
    @State private var scale = 0.5

    var body: some View {
        VStack {
            Circle()
                .scale(scale)
                .animation(.easeInOut, value: scale)
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
- **easeOut**：开始时速度较快，动作结束时速度减慢的动画。
- **easeOut(duration:)**：具有指定持续时间的动画，该动画快速启动，然后在动作结束时变慢。
- **easeInOut(duration:)**：具有指定持续时间的动画，结合了渐进和渐出动画的行为。


---
source: https://developer.apple.com/documentation/SwiftUI/Animation/easeInOut
crawled: 2025-12-03T06:12:09Z
---

# easeInOut

**Type Property**

An animation that combines the behaviors of in and out easing animations.

## Declaration

```swift
static var easeInOut: Animation { get }
```

## Return Value

An ease-in ease-out animation with the default duration.

## Discussion

An easing animation provides motion with a natural feel by varying the acceleration and deceleration of the animation, which matches how things tend to move in reality. An ease in and out animation starts slowly, increasing its speed towards the halfway point, and finally decreasing the speed towards the end of the animation.

The `easeInOut` animation has a default duration of 0.35 seconds. To specify the duration, use the [easeInOut(duration:)](easeInOut_duration.zh-Hans.md) method.

The following code shows an example of animating the size changes of a [Circle](../Circle.zh-Hans.md) using an ease in and out animation.

```swift
struct ContentView: View {
    @State private var scale = 0.5

    var body: some View {
        VStack {
            Circle()
                .scale(scale)
                .animation(.easeInOut, value: scale)
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
- **easeOut**: An animation that starts quickly and then slows towards the end of the movement.
- **easeOut(duration:)**: An animation with a specified duration that starts quickly and then slows towards the end of the movement.
- **easeInOut(duration:)**: An animation with a specified duration that combines the behaviors of in and out easing animations.

