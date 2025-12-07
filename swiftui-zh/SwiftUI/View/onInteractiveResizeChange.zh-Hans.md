--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onInteractiveResizeChange(_:)

抓取时间：2025-11-30T21:10:05Z

---

# onInteractiveResizeChange(_:)

**实例方法**

添加一个在窗口进行交互式调整大小时执行的操作。

## 声明

```swift
nonisolated func onInteractiveResizeChange(_ action: @escaping (Bool) -> Void) -> some View

```

## 参数

- **action**：当窗口的交互式调整大小状态发生变化时要运行的闭包。

## 说明

使用此修饰符可以调整视图在用户调整窗口大小时的行为。传递给此修饰符的操作将在调整大小操作开始和结束时调用。

例如，您可以在交互式调整大小期间调整自定义 Metal 渲染器的帧速率：

```swift
struct RootView: View {
    var renderer: MetalRenderer
    var body: some View {
        MetalRepresentable(renderer: renderer)
           .onInteractiveResizeChange { isResizing in
               // Let the renderer know the window is being actively
               // resized, so that it can adjust frame rate,
               // pause animations, etc.
               renderer.handleWindowResize(isResizing: isResizing)
           }
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/View/onInteractiveResizeChange(_:)
crawled: 2025-11-30T21:10:05Z
---

# onInteractiveResizeChange(_:)

**Instance Method**

Adds an action to perform when the enclosing window is being interactively resized.

## Declaration

```swift
nonisolated func onInteractiveResizeChange(_ action: @escaping (Bool) -> Void) -> some View

```

## Parameters

- **action**: A closure to run when the state of the window’s interactive resize changes.

## Discussion

Use this modifier to adjust how your view behaves when a window is in the process of being resized by the user. The action provided to this modifier will be called when the resize action begins and ends.

For example, you can adjust the frame rate of a custom Metal renderer during interactive resize:

```swift
struct RootView: View {
    var renderer: MetalRenderer
    var body: some View {
        MetalRepresentable(renderer: renderer)
           .onInteractiveResizeChange { isResizing in
               // Let the renderer know the window is being actively
               // resized, so that it can adjust frame rate,
               // pause animations, etc.
               renderer.handleWindowResize(isResizing: isResizing)
           }
    }
}
```

