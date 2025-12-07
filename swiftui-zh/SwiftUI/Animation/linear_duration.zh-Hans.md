---
来源：https://developer.apple.com/documentation/SwiftUI/Animation/linear(持续时间：)
抓取时间： 2025-12-03T06:12:05Z
---

# linear(duration:)

**类型方法**

在指定的持续时间内以恒定速度移动的动画。

## 声明

```swift
static func linear(duration: TimeInterval) -> Animation
```

## 参数

- **duration**：动画完成所需的时间长度（以秒为单位）。

## 返回值

指定持续时间的线性动画。

## 讨论

线性动画的速度从开始到结束都是一致的，因此能给人一种机械运动的感觉。这种恒定的速度使线性动画成为物体运动动画的理想选择，在这种情况下，速度的变化可能会让人感觉突兀，例如活动指示器。

如果要指定动画完成所需的时间，请使用 `linear(duration:)`。否则，请使用 [linear](linear.zh-Hans.md) 在默认时间内执行动画。

下面的代码显示了一个使用持续时间为 2 秒的线性动画的示例，动画演示了一个圆在视图的前缘和后缘之间移动的过程。当圆在视图中移动时，其颜色也会从红色变为蓝色。

```swift
struct ContentView: View {
    @State private var isActive = false

    var body: some View {
        VStack(alignment: isActive ? .trailing : .leading) {
            Circle()
                .fill(isActive ? Color.red : Color.blue)
                .frame(width: 50, height: 50)

            Button("Animate") {
                withAnimation(.linear(duration: 2.0)) {
                    isActive.toggle()
                }
            }
            .frame(maxWidth: .infinity)
        }
    }
}
```



## 获取线性动画

- **linear**：以恒定速度移动的动画。


---
source: https://developer.apple.com/documentation/SwiftUI/Animation/linear(duration:)
crawled: 2025-12-03T06:12:05Z
---

# linear(duration:)

**Type Method**

An animation that moves at a constant speed during a specified duration.

## Declaration

```swift
static func linear(duration: TimeInterval) -> Animation
```

## Parameters

- **duration**: The length of time, expressed in seconds, that the animation takes to complete.

## Return Value

A linear animation with a specified duration.

## Discussion

A linear animation provides a mechanical feel to the motion because its speed is consistent from start to finish of the animation. This constant speed makes a linear animation ideal for animating the movement of objects where changes in the speed might feel awkward, such as with an activity indicator.

Use `linear(duration:)` when you want to specify the time it takes for the animation to complete. Otherwise, use [linear](linear.zh-Hans.md) to perform the animation for a default length of time.

The following code shows an example of using linear animation with a duration of two seconds to animate the movement of a circle as it moves between the leading and trailing edges of the view. The color of the circle also animates from red to blue as it moves across the view.

```swift
struct ContentView: View {
    @State private var isActive = false

    var body: some View {
        VStack(alignment: isActive ? .trailing : .leading) {
            Circle()
                .fill(isActive ? Color.red : Color.blue)
                .frame(width: 50, height: 50)

            Button("Animate") {
                withAnimation(.linear(duration: 2.0)) {
                    isActive.toggle()
                }
            }
            .frame(maxWidth: .infinity)
        }
    }
}
```



## Getting linear animations

- **linear**: An animation that moves at a constant speed.

