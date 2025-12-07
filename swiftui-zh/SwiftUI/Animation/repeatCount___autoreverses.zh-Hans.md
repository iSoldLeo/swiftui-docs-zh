---
来源： https://developer.apple.com/documentation/SwiftUI/Animation/repeatCount(_:autoreverses:)
抓取时间： 2025-12-03T06:12:24Z
---

# repeatCount(_:autoreverses:)

**实例方法**

重复播放指定次数的动画。

## 声明

```swift
func repeatCount(_ repeatCount: Int, autoreverses: Bool = true) -> Animation
```

## 参数

- **repeatCount**：动画重复的次数。当 `autoreverse` 为 `false` 时，每个重复序列从头开始。
- **autoreverses**：布尔值，表示动画序列正向播放后是否反向播放。自动反转将计入 `repeatCount`。例如，`repeatCount` 为 1 时，动画会正向播放一次，但即使`autoreverse` 为 `true`，动画也不会反向播放。当`autoreverse` 为`true` 且`repeatCount` 为`2` 时，动画会向前移动，然后反转，然后停止。

## 返回值

重复指定次数的动画。

## 讨论

使用此方法可重复播放指定次数的动画。例如，在下面的代码中，动画将一辆卡车从视图的一个边缘移动到另一个边缘。动画会重复播放三次。

```swift
struct ContentView: View {
    @State private var driveForward = true

    private var driveAnimation: Animation {
        .easeInOut
        .repeatCount(3, autoreverses: true)
        .speed(0.5)
    }

    var body: some View {
        VStack(alignment: driveForward ? .leading : .trailing, spacing: 40) {
            Image(systemName: "box.truck")
                .font(.system(size: 48))
                .animation(driveAnimation, value: driveForward)

            HStack {
                Spacer()
                Button("Animate") {
                    driveForward.toggle()
                }
                Spacer()
            }
        }
    }
}
```



动画第一次运行时，卡车从视图的前缘移动到后缘。第二次运行动画时，由于`autoreverse` 是 `true`，卡车从后缘移动到前缘。如果 `autoreverse` 是 `false`，卡车在移动到后缘之前会跳回前缘。动画第三次运行时，卡车会从视图的前缘移动到后缘。

## 配置动画

- **delay(_:)**：将动画的开始时间延迟指定的秒数。
- **repeatForever(autoreverses:)**：在包含动画的视图的生命周期内重复动画。
- **speed(_:)**：通过调整速度改变动画的持续时间。


---
source: https://developer.apple.com/documentation/SwiftUI/Animation/repeatCount(_:autoreverses:)
crawled: 2025-12-03T06:12:24Z
---

# repeatCount(_:autoreverses:)

**Instance Method**

Repeats the animation for a specific number of times.

## Declaration

```swift
func repeatCount(_ repeatCount: Int, autoreverses: Bool = true) -> Animation
```

## Parameters

- **repeatCount**: The number of times that the animation repeats. Each repeated sequence starts at the beginning when `autoreverse` is `false`.
- **autoreverses**: A Boolean value that indicates whether the animation sequence plays in reverse after playing forward. Autoreverse counts towards the `repeatCount`. For instance, a `repeatCount` of one plays the animation forward once, but it doesn’t play in reverse even if `autoreverse` is `true`. When `autoreverse` is `true` and `repeatCount` is `2`, the animation moves forward, then reverses, then stops.

## Return Value

An animation that repeats for specific number of times.

## Discussion

Use this method to repeat the animation a specific number of times. For example, in the following code, the animation moves a truck from one edge of the view to the other edge. It repeats this animation three times.

```swift
struct ContentView: View {
    @State private var driveForward = true

    private var driveAnimation: Animation {
        .easeInOut
        .repeatCount(3, autoreverses: true)
        .speed(0.5)
    }

    var body: some View {
        VStack(alignment: driveForward ? .leading : .trailing, spacing: 40) {
            Image(systemName: "box.truck")
                .font(.system(size: 48))
                .animation(driveAnimation, value: driveForward)

            HStack {
                Spacer()
                Button("Animate") {
                    driveForward.toggle()
                }
                Spacer()
            }
        }
    }
}
```



The first time the animation runs, the truck moves from the leading edge to the trailing edge of the view. The second time the animation runs, the truck moves from the trailing edge to the leading edge because `autoreverse` is `true`. If `autoreverse` were `false`, the truck would jump back to leading edge before moving to the trailing edge. The third time the animation runs, the truck moves from the leading to the trailing edge of the view.

## Configuring an animation

- **delay(_:)**: Delays the start of the animation by the specified number of seconds.
- **repeatForever(autoreverses:)**: Repeats the animation for the lifespan of the view containing the animation.
- **speed(_:)**: Changes the duration of an animation by adjusting its speed.

