---
来源： https://developer.apple.com/documentation/SwiftUI/Animation/linear
抓取时间： 2025-12-03T06:12:04Z
---

# 线性

**类型属性**

以恒定速度移动的动画。

## 声明

```swift
static var linear: Animation { get }
```

## 返回值

默认持续时间的线性动画。

## 讨论

线性动画的速度从开始到结束都是一致的，因此能给人一种机械运动的感觉。这种恒定的速度使线性动画成为物体运动动画的理想选择，在这种情况下，速度的变化可能会让人感觉突兀，例如活动指示器。

下面的代码显示了一个使用线性动画制作圆的运动动画的示例，圆在视图的前缘和后缘之间移动。当圆在视图中移动时，它的颜色也会发生动画变化。

```swift
struct ContentView: View {
    @State private var isActive = false

    var body: some View {
        VStack(alignment: isActive ? .trailing : .leading) {
            Circle()
                .fill(isActive ? Color.red : Color.blue)
                .frame(width: 50, height: 50)

            Button("Animate") {
                withAnimation(.linear) {
                    isActive.toggle()
                }
            }
            .frame(maxWidth: .infinity)
        }
    }
}
```



`linear` 动画的默认持续时间为 0.35 秒。要指定不同的持续时间，请使用 [linear(duration:)](linear_duration.zh-Hans.md)。

## 获取线性动画

- **linear(duration:)**：在指定的持续时间内以恒定速度移动的动画。


---
source: https://developer.apple.com/documentation/SwiftUI/Animation/linear
crawled: 2025-12-03T06:12:04Z
---

# linear

**Type Property**

An animation that moves at a constant speed.

## Declaration

```swift
static var linear: Animation { get }
```

## Return Value

A linear animation with the default duration.

## Discussion

A linear animation provides a mechanical feel to the motion because its speed is consistent from start to finish of the animation. This constant speed makes a linear animation ideal for animating the movement of objects where changes in the speed might feel awkward, such as with an activity indicator.

The following code shows an example of using linear animation to animate the movement of a circle as it moves between the leading and trailing edges of the view. The circle also animates its color change as it moves across the view.

```swift
struct ContentView: View {
    @State private var isActive = false

    var body: some View {
        VStack(alignment: isActive ? .trailing : .leading) {
            Circle()
                .fill(isActive ? Color.red : Color.blue)
                .frame(width: 50, height: 50)

            Button("Animate") {
                withAnimation(.linear) {
                    isActive.toggle()
                }
            }
            .frame(maxWidth: .infinity)
        }
    }
}
```



The `linear` animation has a default duration of 0.35 seconds. To specify a different duration, use [linear(duration:)](linear_duration.zh-Hans.md).

## Getting linear animations

- **linear(duration:)**: An animation that moves at a constant speed during a specified duration.

