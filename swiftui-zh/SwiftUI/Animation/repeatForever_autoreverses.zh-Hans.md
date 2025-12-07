---
来源： https://developer.apple.com/documentation/SwiftUI/Animation/repeatForever(autoreverses:)
抓取时间： 2025-12-03T06:12:25Z
---

# repeatForever(autoreverses:)

**实例方法**

在包含动画的视图的生命周期内重复动画。

## 声明

```swift
func repeatForever(autoreverses: Bool = true) -> Animation
```

## 参数

- **autoreverses**：布尔值，表示动画序列正向播放后是否反向播放。

## 返回值

连续重复播放的动画。

## 讨论

使用此方法可重复播放动画，直至视图实例不复存在或视图的显式或结构特性发生变化。例如，下面的代码会在视图的生命周期内持续旋转一个齿轮符号。

```swift
struct ContentView: View {
    @State private var rotationDegrees = 0.0

    private var animation: Animation {
        .linear
        .speed(0.1)
        .repeatForever(autoreverses: false)
    }

    var body: some View {
        Image(systemName: "gear")
            .font(.system(size: 86))
            .rotationEffect(.degrees(rotationDegrees))
            .onAppear {
                withAnimation(animation) {
                    rotationDegrees = 360.0
                }
            }
    }
}
```



## 配置动画

- **delay(_:)**：将动画的开始时间延迟指定的秒数。
- **repeatCount(_:autoreverses:)**：重复播放指定次数的动画。
- **speed(_:)**：通过调整速度改变动画的持续时间。


---
source: https://developer.apple.com/documentation/SwiftUI/Animation/repeatForever(autoreverses:)
crawled: 2025-12-03T06:12:25Z
---

# repeatForever(autoreverses:)

**Instance Method**

Repeats the animation for the lifespan of the view containing the animation.

## Declaration

```swift
func repeatForever(autoreverses: Bool = true) -> Animation
```

## Parameters

- **autoreverses**: A Boolean value that indicates whether the animation sequence plays in reverse after playing forward.

## Return Value

An animation that continuously repeats.

## Discussion

Use this method to repeat the animation until the instance of the view no longer exists, or the view’s explicit or structural identity changes. For example, the following code continuously rotates a gear symbol for the lifespan of the view.

```swift
struct ContentView: View {
    @State private var rotationDegrees = 0.0

    private var animation: Animation {
        .linear
        .speed(0.1)
        .repeatForever(autoreverses: false)
    }

    var body: some View {
        Image(systemName: "gear")
            .font(.system(size: 86))
            .rotationEffect(.degrees(rotationDegrees))
            .onAppear {
                withAnimation(animation) {
                    rotationDegrees = 360.0
                }
            }
    }
}
```



## Configuring an animation

- **delay(_:)**: Delays the start of the animation by the specified number of seconds.
- **repeatCount(_:autoreverses:)**: Repeats the animation for a specific number of times.
- **speed(_:)**: Changes the duration of an animation by adjusting its speed.

