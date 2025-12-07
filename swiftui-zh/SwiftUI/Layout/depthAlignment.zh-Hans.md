---
来源： https://developer.apple.com/documentation/SwiftUI/Layout/depthAlignment(_:)
抓取时间： 2025-11-30T21:37:56Z
---

# depthAlignment(_:)

**实例方法**

设置此布局的深度对齐方式。

## 声明

```swift
func depthAlignment(_ alignment: DepthAlignment) -> some Layout

```

## 参数

- **alignment**：用于对齐布局子视图的 [DepthAlignment](../DepthAlignment.zh-Hans.md) 值

## 讨论

使用 `depthAlignment(_:)` 来指定一个深度向导，用于对齐该布局的子视图。

在下面的示例中，播放机器人动画的按钮与 `.front` 的 `HStack` 对齐。

```swift
   let depthStack = HStackLayout().depthAlignment(.front)
   depthStack {
       RobotModel()
       Button("Play animation") {
           playRobotAnimation()
       }
       .glassBackgroundEffect()
   }
```


---
source: https://developer.apple.com/documentation/SwiftUI/Layout/depthAlignment(_:)
crawled: 2025-11-30T21:37:56Z
---

# depthAlignment(_:)

**Instance Method**

Sets the depth alignment for this layout.

## Declaration

```swift
func depthAlignment(_ alignment: DepthAlignment) -> some Layout

```

## Parameters

- **alignment**: A [DepthAlignment](../DepthAlignment.zh-Hans.md) value to use for aligning layout’s subviews

## Discussion

Use `depthAlignment(_:)` to specify a depth guide for aligning subviews of this layout.

In the example below, the button to play the robot animation is aligned to the `.front` of the `HStack`.

```swift
   let depthStack = HStackLayout().depthAlignment(.front)
   depthStack {
       RobotModel()
       Button("Play animation") {
           playRobotAnimation()
       }
       .glassBackgroundEffect()
   }
```

