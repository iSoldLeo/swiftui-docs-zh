--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onContinuousHover(coordinateSpace:perform:)-8gyrl

抓取时间：2025-12-03T05:35:53Z

---

# onContinuousHover(coordinateSpace:perform:)

**实例方法**

添加一个操作，当指针进入、移动到视图边界内或离开视图边界时执行该操作。

## 声明

```swift
nonisolated func onContinuousHover(coordinateSpace: CoordinateSpace = .local, perform action: @escaping (HoverPhase) -> Void) -> some View

```

## 参数

- **coordinateSpace**：位置值的坐标空间。默认为 [local](../CoordinateSpace/local.zh-Hans.md)。

- **action**：指针进入、移动到视图边界内或离开视图边界时要执行的操作。如果指针位于视图边界内，`action` 闭包会将指针坐标传递给 [active(_:)](../HoverPhase/active.zh-Hans.md) 阶段；否则，它会传递 [ended](../HoverPhase/ended.zh-Hans.md)。

## 返回值

当指针进入、移动到视图边界内或离开视图边界时，会调用 `action` 的视图。

## 说明

调用此方法可以定义一个用于检测指针移动的区域，该区域的大小和位置与此视图相同。以下示例会根据传递给闭包的阶段更新 `hoverLocation` 和 `isHovering`：

```swift
@State private var hoverLocation: CGPoint = .zero
@State private var isHovering = false

var body: some View {
    VStack {
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
                    .foregroundColor(isHovering ? .green : .blue)
                    .offset(x: hoverLocation.x, y: hoverLocation.y)
            }
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/View/onContinuousHover(coordinateSpace:perform:)-8gyrl
crawled: 2025-12-03T05:35:53Z
---

# onContinuousHover(coordinateSpace:perform:)

**Instance Method**

Adds an action to perform when the pointer enters, moves within, and exits the view’s bounds.

## Declaration

```swift
nonisolated func onContinuousHover(coordinateSpace: CoordinateSpace = .local, perform action: @escaping (HoverPhase) -> Void) -> some View

```

## Parameters

- **coordinateSpace**: The coordinate space for the location values. Defaults to [local](../CoordinateSpace/local.zh-Hans.md).
- **action**: The action to perform whenever the pointer enters, moves within, or exits the view’s bounds. The `action` closure passes the [active(_:)](../HoverPhase/active.zh-Hans.md) phase with the pointer’s coordinates if the pointer is in the view’s bounds; otherwise, it passes [ended](../HoverPhase/ended.zh-Hans.md).

## Return Value

A view that calls `action` when the pointer enters, moves within, or exits the view’s bounds.

## Discussion

Call this method to define a region for detecting pointer movement with the size and position of this view. The following example updates `hoverLocation` and `isHovering` to be based on the phase provided to the closure:

```swift
@State private var hoverLocation: CGPoint = .zero
@State private var isHovering = false

var body: some View {
    VStack {
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
                    .foregroundColor(isHovering ? .green : .blue)
                    .offset(x: hoverLocation.x, y: hoverLocation.y)
            }
    }
}
```

