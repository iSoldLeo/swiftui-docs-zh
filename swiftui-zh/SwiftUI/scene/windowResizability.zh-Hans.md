--- 来源：https://developer.apple.com/documentation/SwiftUI/Scene/windowResizability(_:)

抓取时间：2025-12-02T17:21:15Z

---

# windowResizability(_:)

**实例方法**

设置窗口使用的可调整大小类型。

## 声明

```swift
nonisolated func windowResizability(_ resizability: WindowResizability) -> some Scene

```

## 参数

- **resizability**：此场景创建的窗口使用的可调整大小类型。

## 返回值

使用指定可调整大小策略的场景。

## 说明

使用此场景修饰符将 [WindowResizability](../WindowResizability.zh-Hans.md) 类型的值应用于您在 [App](../App.zh-Hans.md) 声明中定义的 [Scene](../Scene.zh-Hans.md)。您指定的值指示系统用于对从该场景创建的窗口施加最小和最大尺寸限制的策略。

例如，您可以创建一个窗口组，用户可以将其大小调整为 100 到 400 点之间。方法是：将具有这些约束的框架应用于场景内容，并将 [contentSize](../WindowResizability/contentSize.zh-Hans.md) 可调整大小属性应用于场景：

```swift
@main
struct MyApp: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
                .frame(
                    minWidth: 100, maxWidth: 400,
                    minHeight: 100, maxHeight: 400)
        }
        .windowResizability(.contentSize)
    }
}
```

如果您不应用此修改器，则所有场景的默认值为 [automatic](../WindowResizability/automatic.zh-Hans.md)。使用此策略时，[Settings](../Settings.zh-Hans.md) 窗口使用 [contentSize](../WindowResizability/contentSize.zh-Hans.md) 策略，而所有其他窗口使用 [contentMinSize](../WindowResizability/contentMinSize.zh-Hans.md) 策略。

## 调整窗口大小

- **定位和调整窗口大小**：影响应用程序显示的窗口的初始几何形状。

- **defaultSize(_:)**：设置窗口的默认大小。

- **defaultSize(width:height:)**：设置窗口的默认宽度和高度。

- **defaultSize(width:height:depth:)**：设置体积窗口的默认大小。

- **defaultSize(_:in:)**：设置体积窗口的默认大小。

- **defaultSize(width:height:depth:in:)**：设置体积窗口的默认大小。

- **WindowResizability**：窗口的可调整大小。

- **windowIdealSize(_:)**：指定从此场景派生的窗口在缩放时如何确定其大小。

- **WindowIdealSize**：定义窗口在缩放时应使用的大小的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/Scene/windowResizability(_:)
crawled: 2025-12-02T17:21:15Z
---

# windowResizability(_:)

**Instance Method**

Sets the kind of resizability to use for a window.

## Declaration

```swift
nonisolated func windowResizability(_ resizability: WindowResizability) -> some Scene

```

## Parameters

- **resizability**: The resizability to use for windows created by this scene.

## Return Value

A scene that uses the specified resizability strategy.

## Discussion

Use this scene modifier to apply a value of type [WindowResizability](../WindowResizability.zh-Hans.md) to a [Scene](../Scene.zh-Hans.md) that you define in your [App](../App.zh-Hans.md) declaration. The value that you specify indicates the strategy the system uses to place minimum and maximum size restrictions on windows that it creates from that scene.

For example, you can create a window group that people can resize to between 100 and 400 points in both dimensions by applying both a frame with those constraints to the scene’s content, and the [contentSize](../WindowResizability/contentSize.zh-Hans.md) resizability to the scene:

```swift
@main
struct MyApp: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
                .frame(
                    minWidth: 100, maxWidth: 400,
                    minHeight: 100, maxHeight: 400)
        }
        .windowResizability(.contentSize)
    }
}
```

The default value for all scenes if you don’t apply the modifier is [automatic](../WindowResizability/automatic.zh-Hans.md). With that strategy, [Settings](../Settings.zh-Hans.md) windows use the [contentSize](../WindowResizability/contentSize.zh-Hans.md) strategy, while all others use [contentMinSize](../WindowResizability/contentMinSize.zh-Hans.md).

## Sizing a window

- **Positioning and sizing windows**: Influence the initial geometry of windows that your app presents.
- **defaultSize(_:)**: Sets a default size for a window.
- **defaultSize(width:height:)**: Sets a default width and height for a window.
- **defaultSize(width:height:depth:)**: Sets a default size for a volumetric window.
- **defaultSize(_:in:)**: Sets a default size for a volumetric window.
- **defaultSize(width:height:depth:in:)**: Sets a default size for a volumetric window.
- **WindowResizability**: The resizability of a window.
- **windowIdealSize(_:)**: Specifies how windows derived form this scene should determine their size when zooming.
- **WindowIdealSize**: A type which defines the size a window should use when zooming.

