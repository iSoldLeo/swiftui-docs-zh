---
来源： https://developer.apple.com/documentation/swiftui/customanimation
抓取时间： 2025-12-04T13:13:48Z
---

# 自定义动画

**Protocol**

一种定义动画值如何随时间变化的类型。

### 声明

```swift
@preconcurrency protocol CustomAnimation : Hashable, Sendable
```

## 概览

使用本协议可创建一种随时间改变动画值的类型，从而产生视图的自定义可视化过渡。例如，以下代码使用弹性易入易出函数来改变动画值：

```swift
struct ElasticEaseInEaseOutAnimation: CustomAnimation {
    let duration: TimeInterval

    func animate<V>(value: V, time: TimeInterval, context: inout AnimationContext<V>) -> V? where V : VectorArithmetic {
        if time > duration { return nil } // The animation has finished.

        let p = time / duration
        let s = sin((20 * p - 11.125) * ((2 * Double.pi) / 4.5))
        if p < 0.5 {
            return value.scaled(by: -(pow(2, 20 * p - 10) * s) / 2)
        } else {
            return value.scaled(by: (pow(2, -20 * p + 10) * s) / 2 + 1)
        }
    }
}
```



要创建自定义动画的 [Animation](Animation.zh-Hans.md) 实例，请使用 [init(_:)](Animation/init.zh-Hans.md) 初始化器，并传入自定义动画的实例；例如

```swift
Animation(ElasticEaseInEaseOutAnimation(duration: 5.0))
```

为使视图代码更易读，可扩展[Animation](Animation.zh-Hans.md) 并添加静态属性和函数，以返回自定义动画的`Animation` 实例。例如，下面的代码添加了静态属性 `elasticEaseInEaseOut`，返回默认持续时间为 `0.35` 秒的弹性缓入缓出动画。接下来，代码添加了一个方法，用于返回指定持续时间的动画。

```swift
extension Animation {
    static var elasticEaseInEaseOut: Animation { elasticEaseInEaseOut(duration: 0.35) }
    static func elasticEaseInEaseOut(duration: TimeInterval) -> Animation {
        Animation(ElasticEaseInEaseOutAnimation(duration: duration))
    }
}
```

要使用弹性缓入缓出动画为视图制作动画，视图需要调用`.elasticEaseInEaseOut` 或 `.elasticEaseInEaseOut(duration:)`。例如，下面的代码包含一个 Animate 按钮，点击该按钮后，视图中的一个圆会从视图的一个边缘移动到另一个边缘，该动画使用的是持续时间为 `5` 秒的弹性易入易出动画：

```swift
struct ElasticEaseInEaseOutView: View {
    @State private var isActive = false

    var body: some View {
        VStack(alignment: isActive ? .trailing : .leading) {
            Circle()
                .frame(width: 100.0)
                .foregroundColor(.accentColor)

            Button("Animate") {
                withAnimation(.elasticEaseInEaseOut(duration: 5.0)) {
                    isActive.toggle()
                }
            }
            .frame(maxWidth: .infinity)
        }
        .padding()
    }
}
```



## 动画值

- **animate(value:time:context:)**：计算指定时间的动画值。

## 获取速度

- **velocity(value:time:context:)**：计算动画在指定时间的速度。

## 确定是否合并

- **shouldMerge(previous:value:time:context:)**：决定动画实例是否可以与其他同类型实例合并。

## 创建自定义动画

- **AnimationContext**：自定义动画可用于管理状态和访问视图环境的上下文值。
- **AnimationState**：存储自定义动画状态的容器。
- **AnimationStateKey**：用于访问动画状态值的键。
- **UnitCurve**：由二维曲线定义的函数，用于将范围为 [0,1] 的输入进度映射到范围同样为 [0,1] 的输出进度。通过改变曲线的形状，可以改变动画或其他插值的有效速度。
- **Spring**：弹簧运动的表示。

## 继承自

- 等价
- Hashable
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/swiftui/customanimation
crawled: 2025-12-04T13:13:48Z
---

# CustomAnimation

**Protocol**

A type that defines how an animatable value changes over time.

## Declaration

```swift
@preconcurrency protocol CustomAnimation : Hashable, Sendable
```

## Overview

Use this protocol to create a type that changes an animatable value over time, which produces a custom visual transition of a view. For example, the follow code changes an animatable value using an elastic ease-in ease-out function:

```swift
struct ElasticEaseInEaseOutAnimation: CustomAnimation {
    let duration: TimeInterval

    func animate<V>(value: V, time: TimeInterval, context: inout AnimationContext<V>) -> V? where V : VectorArithmetic {
        if time > duration { return nil } // The animation has finished.

        let p = time / duration
        let s = sin((20 * p - 11.125) * ((2 * Double.pi) / 4.5))
        if p < 0.5 {
            return value.scaled(by: -(pow(2, 20 * p - 10) * s) / 2)
        } else {
            return value.scaled(by: (pow(2, -20 * p + 10) * s) / 2 + 1)
        }
    }
}
```



To create an [Animation](Animation.zh-Hans.md) instance of a custom animation, use the [init(_:)](Animation/init.zh-Hans.md) initializer, passing in an instance of a custom animation; for example:

```swift
Animation(ElasticEaseInEaseOutAnimation(duration: 5.0))
```

To help make view code more readable, extend [Animation](Animation.zh-Hans.md) and add a static property and function that returns an `Animation` instance of a custom animation. For example, the following code adds the static property `elasticEaseInEaseOut` that returns the elastic ease-in ease-out animation with a default duration of `0.35` seconds. Next, the code adds a method that returns the animation with a specified duration.

```swift
extension Animation {
    static var elasticEaseInEaseOut: Animation { elasticEaseInEaseOut(duration: 0.35) }
    static func elasticEaseInEaseOut(duration: TimeInterval) -> Animation {
        Animation(ElasticEaseInEaseOutAnimation(duration: duration))
    }
}
```

To animate a view with the elastic ease-in ease-out animation, a view calls either `.elasticEaseInEaseOut` or `.elasticEaseInEaseOut(duration:)`. For example, the follow code includes an Animate button that, when clicked, animates a circle as it moves from one edge of the view to the other, using the elastic ease-in ease-out animation with a duration of `5` seconds:

```swift
struct ElasticEaseInEaseOutView: View {
    @State private var isActive = false

    var body: some View {
        VStack(alignment: isActive ? .trailing : .leading) {
            Circle()
                .frame(width: 100.0)
                .foregroundColor(.accentColor)

            Button("Animate") {
                withAnimation(.elasticEaseInEaseOut(duration: 5.0)) {
                    isActive.toggle()
                }
            }
            .frame(maxWidth: .infinity)
        }
        .padding()
    }
}
```



## Animating a value

- **animate(value:time:context:)**: Calculates the value of the animation at the specified time.

## Getting the velocity

- **velocity(value:time:context:)**: Calculates the velocity of the animation at a specified time.

## Determining whether to merge

- **shouldMerge(previous:value:time:context:)**: Determines whether an instance of the animation can merge with other instance of the same type.

## Creating custom animations

- **AnimationContext**: Contextual values that a custom animation can use to manage state and access a view’s environment.
- **AnimationState**: A container that stores the state for a custom animation.
- **AnimationStateKey**: A key for accessing animation state values.
- **UnitCurve**: A  function defined by a two-dimensional curve that maps an input progress in the range [0,1] to an output progress that is also in the range [0,1]. By changing the shape of the curve, the effective speed of an animation or other interpolation can be changed.
- **Spring**: A representation of a spring’s motion.

## Inherits From

- Equatable
- Hashable
- Sendable
- SendableMetatype

