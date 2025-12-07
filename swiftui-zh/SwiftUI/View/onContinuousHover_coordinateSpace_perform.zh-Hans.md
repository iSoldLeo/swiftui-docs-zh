--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onContinuousHover(coordinateSpace:perform:)

抓取时间：2025-12-02T17:41:48Z

---

# onContinuousHover(coordinateSpace:perform:)

**实例方法**

添加一个操作，当指针进入、移动到视图边界内或离开视图边界时执行该操作。

## 声明

```swift
nonisolated func onContinuousHover(coordinateSpace: some CoordinateSpaceProtocol = .local, perform action: @escaping (HoverPhase) -> Void) -> some View

```

## 参数

- **coordinateSpace**：位置值的坐标空间。默认值为 [local](../CoordinateSpace/local.zh-Hans.md)。

- **action**：指针进入、移动到视图边界内或离开视图边界时要执行的操作。闭包接收一个 `phase` 输入，其值为 [active(_:)](../HoverPhase/active.zh-Hans.md)，包含指针在视图边界内的坐标。当指针离开视图边界时，闭包接收 [ended](../HoverPhase/ended.zh-Hans.md) 阶段。

## 返回值

一个视图，当指针进入、移动到视图边界内或离开视图边界时，该视图会调用 `action`。

## 说明

使用此修饰符定义一个区域，用于检测视图中的指针移动。以下示例通过修改 `hoverLocation` 和 `isHovering` 的值，来更新小矩形的位置和样式，同时指针在较大的红色矩形内移动：

```swift
@State private var hoverLocation: CGPoint = .zero
@State private var isHovering = false

var body: some View {
    Color.red
        .frame(width: 400, height: 400)
        .onContinuousHover { phase in
            switch phase {
            case .active(let location):
                hoverLocation = location
                isHovering = true
            case .ended:
                isHovering = false
            }
        }
        .overlay {
            Rectangle()
                .frame(width: 50, height: 50)
                .foregroundStyle(isHovering ? .green : .blue)
                .offset(x: hoverLocation.x, y: hoverLocation.y)
        }
}
```

## 响应悬停事件

- **onHover(perform:)**：添加一个操作，当用户将指针移到视图框架上方或下方时执行。

- **hoverEffect(_:isEnabled:)**：为该视图应用悬停效果。

- **hoverEffectDisabled(_:)**：添加一个条件，用于控制该视图是否可以显示悬停效果。

- **defaultHoverEffect(_:)**：设置此视图内其他视图使用的默认悬停效果。

- **isHoverEffectEnabled**：一个布尔值，指示与此环境关联的视图是否允许显示悬停效果。

- **HoverPhase**：指针的当前悬停状态和值。

- **HoverEffectPhaseOverride**：用于覆盖悬停效果当前阶段的选项。

- **OrnamentHoverContentEffect**：使用自定义效果在悬停时显示装饰物。

- **OrnamentHoverEffect**：在悬停时显示装饰物。


---
source: https://developer.apple.com/documentation/SwiftUI/View/onContinuousHover(coordinateSpace:perform:)
crawled: 2025-12-02T17:41:48Z
---

# onContinuousHover(coordinateSpace:perform:)

**Instance Method**

Adds an action to perform when the pointer enters, moves within, and exits the view’s bounds.

## Declaration

```swift
nonisolated func onContinuousHover(coordinateSpace: some CoordinateSpaceProtocol = .local, perform action: @escaping (HoverPhase) -> Void) -> some View

```

## Parameters

- **coordinateSpace**: The coordinate space for the location values. The default value is [local](../CoordinateSpace/local.zh-Hans.md).
- **action**: The action to perform whenever the pointer enters, moves within, or exits the view’s bounds. The closure takes a `phase` input that has the value [active(_:)](../HoverPhase/active.zh-Hans.md) and contains the pointer’s coordinates if the pointer is within the view’s bounds. The closure receives the [ended](../HoverPhase/ended.zh-Hans.md) phase when the pointer leaves the view’s bounds.

## Return Value

A view that calls `action` when the pointer enters, moves within, or exits the view’s bounds.

## Discussion

Use this modifier to define a region for detecting pointer movement with a view. The following example updates a small rectangle’s position and style by modifying `hoverLocation` and `isHovering` as the pointer moves within the larger, red rectangle:

```swift
@State private var hoverLocation: CGPoint = .zero
@State private var isHovering = false

var body: some View {
    Color.red
        .frame(width: 400, height: 400)
        .onContinuousHover { phase in
            switch phase {
            case .active(let location):
                hoverLocation = location
                isHovering = true
            case .ended:
                isHovering = false
            }
        }
        .overlay {
            Rectangle()
                .frame(width: 50, height: 50)
                .foregroundStyle(isHovering ? .green : .blue)
                .offset(x: hoverLocation.x, y: hoverLocation.y)
        }
}
```

## Responding to hover events

- **onHover(perform:)**: Adds an action to perform when the user moves the pointer over or away from the view’s frame.
- **hoverEffect(_:isEnabled:)**: Applies a hover effect to this view.
- **hoverEffectDisabled(_:)**: Adds a condition that controls whether this view can display hover effects.
- **defaultHoverEffect(_:)**: Sets the default hover effect to use for views within this view.
- **isHoverEffectEnabled**: A Boolean value that indicates whether the view associated with this environment allows hover effects to be displayed.
- **HoverPhase**: The current hovering state and value of the pointer.
- **HoverEffectPhaseOverride**: Options for overriding a hover effect’s current phase.
- **OrnamentHoverContentEffect**: Presents an ornament on hover using a custom effect.
- **OrnamentHoverEffect**: Presents an ornament on hover.

