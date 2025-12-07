--- 来源：https://developer.apple.com/documentation/SwiftUI/Scene/windowIdealSize(_:)

抓取时间：2025-12-02T17:21:16Z

---

# windowIdealSize(_:)

**实例方法**

指定从该场景派生的窗口在缩放时如何确定自身大小。

## 声明

```swift
nonisolated func windowIdealSize(_ idealSize: WindowIdealSize) -> some Scene

```

## 参数

- **idealSize**：一个值，用于确定从该场景派生的窗口在缩放时如何调整自身大小。

## 说明

默认情况下，窗口大小将设置为其最大尺寸或显示边界，以较小者为准。通过重写此行为，您可以为窗口内容提供合适的大小。

例如，您可以定义一个窗口组，其中窗口的理想宽度为 800 点，理想高度为 600 点：

```swift
struct MyApp: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
                .frame(idealWidth: 800, idealHeight: 600)
        }
        .windowIdealSize(.fitToContent)
    }
}
```

## 调整窗口大小

- **定位和调整窗口大小**：影响应用程序显示的窗口的初始几何形状。

- **defaultSize(_:)**：设置窗口的默认大小。

- **defaultSize(width:height:)**：设置窗口的默认宽度和高度。

- **defaultSize(width:height:depth:)**：设置体感窗口的默认大小。

- **defaultSize(_:in:)**：设置体感窗口的默认大小。

- **defaultSize(width:height:depth:in:)**：设置体感窗口的默认大小。

- **windowResizability(_:)**：设置窗口的可调整大小类型。

- **WindowResizability**：窗口的可调整大小。

- **WindowIdealSize**：定义窗口缩放时应使用的尺寸类型。


---
source: https://developer.apple.com/documentation/SwiftUI/Scene/windowIdealSize(_:)
crawled: 2025-12-02T17:21:16Z
---

# windowIdealSize(_:)

**Instance Method**

Specifies how windows derived form this scene should determine their size when zooming.

## Declaration

```swift
nonisolated func windowIdealSize(_ idealSize: WindowIdealSize) -> some Scene

```

## Parameters

- **idealSize**: A value which determines how windows derived from this scene should size themselves when zooming.

## Discussion

The default behavior will size the window to its maximum size, or the bounds of the display, whichever is smaller. By overriding this behavior, you can provide a size that is appropriate for the contents of your window.

For example, you can define a window group where the window has an ideal width of 800 points and an ideal height of 600 points:

```swift
struct MyApp: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
                .frame(idealWidth: 800, idealHeight: 600)
        }
        .windowIdealSize(.fitToContent)
    }
}
```

## Sizing a window

- **Positioning and sizing windows**: Influence the initial geometry of windows that your app presents.
- **defaultSize(_:)**: Sets a default size for a window.
- **defaultSize(width:height:)**: Sets a default width and height for a window.
- **defaultSize(width:height:depth:)**: Sets a default size for a volumetric window.
- **defaultSize(_:in:)**: Sets a default size for a volumetric window.
- **defaultSize(width:height:depth:in:)**: Sets a default size for a volumetric window.
- **windowResizability(_:)**: Sets the kind of resizability to use for a window.
- **WindowResizability**: The resizability of a window.
- **WindowIdealSize**: A type which defines the size a window should use when zooming.

