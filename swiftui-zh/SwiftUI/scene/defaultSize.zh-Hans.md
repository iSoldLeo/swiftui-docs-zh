--- 来源：https://developer.apple.com/documentation/SwiftUI/Scene/defaultSize(_:)

抓取时间：2025-11-30T21:06:16Z

---

# defaultSize(_:)

**实例方法**

设置窗口的默认大小。

## 声明

```swift
nonisolated func defaultSize(_ size: CGSize) -> some Scene

```

## 参数

- **size**：从场景创建的新窗口的默认大小。

## 返回值

一个使用默认大小创建新窗口的场景。

## 说明

使用此场景修饰符来指定系统从 [Scene](../Scene.zh-Hans.md) 声明创建的新窗口的默认初始大小。例如，您可以请求 [WindowGroup](../WindowGroup.zh-Hans.md) 生成的新窗口在 x 轴方向上占据 600 个点，在 y 轴方向上占据 400 个点：

```swift
@main
struct MyApp: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
        }
        .defaultSize(CGSize(width: 600, height: 400))
    }
}
```

您指定的尺寸仅作为窗口首次出现时的默认尺寸。用户之后可以使用系统提供的界面控件调整窗口大小。此外，在状态恢复期间，系统会将窗口恢复到其最近一次调整后的大小，而不是默认大小。

如果您指定的默认尺寸超出窗口在一个或两个方向上的固有可调整大小范围，系统会限制受影响的方向，使其保持在范围内。您可以使用 [windowResizability(_:)](windowResizability.zh-Hans.md) 修改器配置场景的可调整大小。

默认尺寸修改器会影响 macOS 中所有创建窗口的场景类型，具体包括：

- [WindowGroup](../WindowGroup.zh-Hans.md)

- [Window](../Window.zh-Hans.md)

- [DocumentGroup](../DocumentGroup.zh-Hans.md)

- [Settings](../Settings.zh-Hans.md)

如果您想直接指定窗口的宽度和高度，请改用 [defaultSize(width:height:)](defaultSize_width_height.zh-Hans.md)。

## 调整窗口大小

- **定位和调整窗口大小**：影响应用程序显示的窗口的初始几何形状。

- **defaultSize(width:height:)**：设置窗口的默认宽度和高度。

- **defaultSize(width:height:depth:)**：设置体积窗口的默认大小。

- **defaultSize(_:in:)**：设置体积窗口的默认大小。

- **defaultSize(width:height:depth:in:)**：设置体积窗口的默认大小。

- **windowResizability(_:)**：设置窗口的可调整大小方式。

- **WindowResizability**：窗口的可调整大小。

- **windowIdealSize(_:)**：指定从此场景派生的窗口在缩放时如何确定其大小。

- **WindowIdealSize**：定义窗口在缩放时应使用的大小的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/Scene/defaultSize(_:)
crawled: 2025-11-30T21:06:16Z
---

# defaultSize(_:)

**Instance Method**

Sets a default size for a window.

## Declaration

```swift
nonisolated func defaultSize(_ size: CGSize) -> some Scene

```

## Parameters

- **size**: The default size for new windows created from a scene.

## Return Value

A scene that uses a default size for new windows.

## Discussion

Use this scene modifier to indicate a default initial size for a new window that the system creates from a [Scene](../Scene.zh-Hans.md) declaration. For example, you can request that new windows that a [WindowGroup](../WindowGroup.zh-Hans.md) generates occupy 600 points in the x-dimension and 400 points in the y-dimension:

```swift
@main
struct MyApp: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
        }
        .defaultSize(CGSize(width: 600, height: 400))
    }
}
```

The size that you specify acts only as a default for when the window first appears. People can later resize the window using interface controls that the system provides. Also, during state restoration, the system restores windows to their most recent size rather than the default size.

If you specify a default size that’s outside the range of the window’s inherent resizability in one or both dimensions, the system clamps the affected dimension to keep it in range. You can configure the resizability of a scene using the [windowResizability(_:)](windowResizability.zh-Hans.md) modifier.

The default size modifier affects any scene type that creates windows in macOS, namely:

- [WindowGroup](../WindowGroup.zh-Hans.md)
- [Window](../Window.zh-Hans.md)
- [DocumentGroup](../DocumentGroup.zh-Hans.md)
- [Settings](../Settings.zh-Hans.md)

If you want to specify the input directly in terms of width and height, use [defaultSize(width:height:)](defaultSize_width_height.zh-Hans.md) instead.

## Sizing a window

- **Positioning and sizing windows**: Influence the initial geometry of windows that your app presents.
- **defaultSize(width:height:)**: Sets a default width and height for a window.
- **defaultSize(width:height:depth:)**: Sets a default size for a volumetric window.
- **defaultSize(_:in:)**: Sets a default size for a volumetric window.
- **defaultSize(width:height:depth:in:)**: Sets a default size for a volumetric window.
- **windowResizability(_:)**: Sets the kind of resizability to use for a window.
- **WindowResizability**: The resizability of a window.
- **windowIdealSize(_:)**: Specifies how windows derived form this scene should determine their size when zooming.
- **WindowIdealSize**: A type which defines the size a window should use when zooming.

