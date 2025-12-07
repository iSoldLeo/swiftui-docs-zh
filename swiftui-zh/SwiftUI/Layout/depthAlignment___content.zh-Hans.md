---
来源： https://developer.apple.com/documentation/SwiftUI/Layout/depthAlignment(_:content:)
抓取时间： 2025-12-02T17:53:13Z
---

# depthAlignment(_:content:)

**实例方法**

按照指定的深度对齐方式创建布局视图。

## 声明

```swift
nonisolated func depthAlignment<Content>(_ alignment: DepthAlignment, @ViewBuilder content: () -> Content) -> some View where Content : View

```

## 参数

- **alignment**：用于对齐布局子视图的 [DepthAlignment](../DepthAlignment.zh-Hans.md) 值

## 讨论

使用 `depthAlignment(_:content:)` 来指定一个深度向导，用于对齐该布局的子视图。

在下面的示例中，播放机器人动画的按钮与 `.front` 的 `HStack` 对齐。

```swift
   HStackLayout().depthAlignment(.front) {
       RobotModel()
       Button("Play animation") {
           playRobotAnimation()
       }
       .glassBackgroundEffect()
   }
```


---
source: https://developer.apple.com/documentation/SwiftUI/Layout/depthAlignment(_:content:)
crawled: 2025-12-02T17:53:13Z
---

# depthAlignment(_:content:)

**Instance Method**

Creates a layout view with the specified depth alignment.

## Declaration

```swift
nonisolated func depthAlignment<Content>(_ alignment: DepthAlignment, @ViewBuilder content: () -> Content) -> some View where Content : View

```

## Parameters

- **alignment**: A [DepthAlignment](../DepthAlignment.zh-Hans.md) value to use for aligning layout’s subviews

## Discussion

Use `depthAlignment(_:content:)` to specify a depth guide for aligning subviews of this layout.

In the example below, the button to play the robot animation is aligned to the `.front` of the `HStack`.

```swift
   HStackLayout().depthAlignment(.front) {
       RobotModel()
       Button("Play animation") {
           playRobotAnimation()
       }
       .glassBackgroundEffect()
   }
```

