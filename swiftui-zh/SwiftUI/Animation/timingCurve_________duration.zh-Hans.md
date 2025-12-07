---
来源：https://developer.apple.com/documentation/SwiftUI/Animation/timingCurve(_:_:_:_:_:_:持续时间:)
抓取时间：2025-12-03T06:12:23Z


# timingCurve(_:_:_:_:duration:)

**类型方法**

根据立方贝塞尔定时曲线创建的动画。

## 声明

```swift
static func timingCurve(_ p1x: Double, _ p1y: Double, _ p2x: Double, _ p2y: Double, duration: TimeInterval = 0.35) -> Animation
```

## 参数

- **p1x**：三次贝塞尔曲线第一个控制点的 x 坐标。
- **p1y**：三次贝塞尔曲线第一个控制点的 Y 坐标。
- **p2x**：三次贝塞尔曲线第二个控制点的 x 坐标。
- **p2y**：三次贝塞尔曲线第二个控制点的 Y 坐标。
- **duration**：动画完成所需的时间长度（以秒为单位）。

## 返回值

立方贝塞尔定时曲线动画。

## 讨论

使用此方法可根据三次贝塞尔曲线的控制点创建定时曲线。立方贝塞尔定时曲线由一条起点为`(0, 0)`、终点为`(1, 1)`的直线组成。另外两个控制点 `(p1x, p1y)` 和 `(p2x, p2y)` 确定了曲线的形状。

直线的斜率定义了动画在该时间点的速度。斜率越大，动画运行速度越快，斜率越小，动画运行速度越慢。下图显示了一条时序曲线，在这条曲线上，动画开始和结束的速度都很快，但在动画的中间部分显得较慢。



下面的代码使用上一插图中的时序曲线，随着[Circle](../Circle.zh-Hans.md) 的大小变化而制作动画。

```swift
struct ContentView: View {
    @State private var scale = 1.0

    var body: some View {
        VStack {
            Circle()
                .scaleEffect(scale)
                .animation(
                    .timingCurve(0.1, 0.75, 0.85, 0.35, duration: 2.0),
                    value: scale)

            Button("Animate") {
                if scale == 1.0 {
                    scale = 0.25
                } else {
                    scale = 1.0
                }
            }
        }
    }
}
```



## 创建自定义动画

- **init(_:)**：创建包含指定自定义动画的`Animation`。
- **timingCurve(_:duration:)**：创建速度由给定曲线控制的新动画。


---
source: https://developer.apple.com/documentation/SwiftUI/Animation/timingCurve(_:_:_:_:duration:)
crawled: 2025-12-03T06:12:23Z
---

# timingCurve(_:_:_:_:duration:)

**Type Method**

An animation created from a cubic Bézier timing curve.

## Declaration

```swift
static func timingCurve(_ p1x: Double, _ p1y: Double, _ p2x: Double, _ p2y: Double, duration: TimeInterval = 0.35) -> Animation
```

## Parameters

- **p1x**: The x-coordinate of the first control point of the cubic Bézier curve.
- **p1y**: The y-coordinate of the first control point of the cubic Bézier curve.
- **p2x**: The x-coordinate of the second control point of the cubic Bézier curve.
- **p2y**: The y-coordinate of the second control point of the cubic Bézier curve.
- **duration**: The length of time, expressed in seconds, the animation takes to complete.

## Return Value

A cubic Bézier timing curve animation.

## Discussion

Use this method to create a timing curve based on the control points of a cubic Bézier curve. A cubic Bézier timing curve consists of a line whose starting point is `(0, 0)` and whose end point is `(1, 1)`. Two additional control points, `(p1x, p1y)` and `(p2x, p2y)`, define the shape of the curve.

The slope of the line defines the speed of the animation at that point in time. A steep slopes causes the animation to appear to run faster, while a shallower slope appears to run slower. The following illustration shows a timing curve where the animation starts and finishes fast, but appears slower through the middle section of the animation.



The following code uses the timing curve from the previous illustration to animate a [Circle](../Circle.zh-Hans.md) as its size changes.

```swift
struct ContentView: View {
    @State private var scale = 1.0

    var body: some View {
        VStack {
            Circle()
                .scaleEffect(scale)
                .animation(
                    .timingCurve(0.1, 0.75, 0.85, 0.35, duration: 2.0),
                    value: scale)

            Button("Animate") {
                if scale == 1.0 {
                    scale = 0.25
                } else {
                    scale = 1.0
                }
            }
        }
    }
}
```



## Creating custom animations

- **init(_:)**: Create an `Animation` that contains the specified custom animation.
- **timingCurve(_:duration:)**: Creates a new animation with speed controlled by the given curve.

