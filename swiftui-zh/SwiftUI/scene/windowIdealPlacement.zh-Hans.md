--- 来源：https://developer.apple.com/documentation/SwiftUI/Scene/windowIdealPlacement(_:)

抓取时间：2025-12-02T17:21:23Z

---

# windowIdealPlacement(_:)

**实例方法**

提供一个函数，用于确定场景窗口缩放时的理想位置。

## 声明

```swift
nonisolated func windowIdealPlacement(_ makePlacement: @escaping (WindowLayoutRoot, WindowPlacementContext) -> WindowPlacement) -> some Scene

```

## 参数

- **makePlacement**：一个闭包，返回从此场景派生的窗口的理想位置。

## 说明

默认情况下，窗口大小会调整为最大尺寸或显示边界，以较小者为准。通过重写此行为，您可以为窗口内容指定合适的大小。

例如，您可以设置窗口的高度等于显示边界，宽度则根据内容的理想宽度来设置：

```swift
struct MyApp: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
        }
        .windowIdealPlacement { content, context in
            let displayBounds = context.defaultDisplay.visibleRect
            let proposal = ProposedViewSize(
                width: nil, height: displayBounds.height)
            let contentSize = content.sizeThatFits(proposal)
            return .init(
                width: contentSize.width,
                height: contentSize.height)
        }
    }
}
```

## 定位窗口

- **defaultPosition(_:)**：设置窗口的默认位置。

- **WindowLevel**：窗口的级别。

- **windowLevel(_:)**：设置此场景的窗口级别。

- **WindowLayoutRoot**：表示窗口根内容的代理。

- **WindowPlacement**：表示窗口首选大小和位置的类型。

- **defaultWindowPlacement(_:)**：定义用于确定窗口默认位置的函数。

- **WindowPlacementContext**：一种用于表示窗口大小和位置的上下文信息的类型。

- **WindowProxy**：应用程序中已打开窗口的代理。

- **DisplayProxy**：一种提供有关显示硬件信息的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/Scene/windowIdealPlacement(_:)
crawled: 2025-12-02T17:21:23Z
---

# windowIdealPlacement(_:)

**Instance Method**

Provides a function which determines a placement to use when windows of a scene zoom.

## Declaration

```swift
nonisolated func windowIdealPlacement(_ makePlacement: @escaping (WindowLayoutRoot, WindowPlacementContext) -> WindowPlacement) -> some Scene

```

## Parameters

- **makePlacement**: A closure which returns the ideal placement for a window derived from this scene.

## Discussion

The default behavior will size the window to its maximum size, or the bounds of the display, whichever is smaller. By overriding this behavior, you can provide a size that is appropriate for the contents of your window.

For example, you can provide a placement with a height equal to the display bounds, and a width based on your content’s ideal width:

```swift
struct MyApp: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
        }
        .windowIdealPlacement { content, context in
            let displayBounds = context.defaultDisplay.visibleRect
            let proposal = ProposedViewSize(
                width: nil, height: displayBounds.height)
            let contentSize = content.sizeThatFits(proposal)
            return .init(
                width: contentSize.width,
                height: contentSize.height)
        }
    }
}
```

## Positioning a window

- **defaultPosition(_:)**: Sets a default position for a window.
- **WindowLevel**: The level of a window.
- **windowLevel(_:)**: Sets the window level of this scene.
- **WindowLayoutRoot**: A proxy which represents the root contents of a window.
- **WindowPlacement**: A type which represents a preferred size and position for a window.
- **defaultWindowPlacement(_:)**: Defines a function used for determining the default placement of windows.
- **WindowPlacementContext**: A type which represents contextual information used for sizing and positioning windows.
- **WindowProxy**: The proxy for an open window in the app.
- **DisplayProxy**: A type which provides information about display hardware.

