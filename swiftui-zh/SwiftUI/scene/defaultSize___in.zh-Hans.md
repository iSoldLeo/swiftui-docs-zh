--- 来源：https://developer.apple.com/documentation/SwiftUI/Scene/defaultSize(_:in:)

抓取时间：2025-11-30T21:06:18Z

---

# defaultSize(_:in:)

**实例方法**

设置体积窗口的默认大小。

## 声明

```swift
nonisolated func defaultSize(_ size: Size3D, in unit: UnitLength) -> some Scene

```

## 参数

- **unit**：窗口尺寸的长度单位。

## 返回值

一个使用默认大小创建新窗口的场景。

## 讨论

使用此修改器指定使用 [VolumetricWindowStyle](../VolumetricWindowStyle.zh-Hans.md) 从 [Scene](../Scene.zh-Hans.md) 创建的新 3D 窗口的默认初始大小：

```swift
WindowGroup {
    ContentView()
}
.windowStyle(.volumetric)
.defaultSize(Size3D(width: 1, height: 1, depth: 0.5), in: .meters)
```

每个参数均以您提供的单位指定。体积场景的大小在创建后不可更改。

此修改器仅影响 visionOS 中具有体积样式的窗口。

## 调整窗口大小

- **定位和调整窗口大小**：影响应用程序显示的窗口的初始几何形状。

- **defaultSize(_:)**：设置窗口的默认大小。

- **defaultSize(width:height:)**：设置窗口的默认宽度和高度。

- **defaultSize(width:height:depth:)**：设置体积窗口的默认大小。

- **defaultSize(width:height:depth:in:)**：设置体积窗口的默认大小。

- **windowResizability(_:)**：设置窗口的可调整大小方式。

- **WindowResizability**：窗口的可调整大小。

- **windowIdealSize(_:)**：指定从此场景派生的窗口在缩放时如何确定其大小。

- **WindowIdealSize**：定义窗口在缩放时应使用的大小的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/Scene/defaultSize(_:in:)
crawled: 2025-11-30T21:06:18Z
---

# defaultSize(_:in:)

**Instance Method**

Sets a default size for a volumetric window.

## Declaration

```swift
nonisolated func defaultSize(_ size: Size3D, in unit: UnitLength) -> some Scene

```

## Parameters

- **unit**: The unit of length the dimensions of the window are specified in.

## Return Value

A scene that uses a default size for new windows.

## Discussion

Use this modifier to indicate the default initial size for a new 3D window created from a [Scene](../Scene.zh-Hans.md) using [VolumetricWindowStyle](../VolumetricWindowStyle.zh-Hans.md):

```swift
WindowGroup {
    ContentView()
}
.windowStyle(.volumetric)
.defaultSize(Size3D(width: 1, height: 1, depth: 0.5), in: .meters)
```

Each parameter is specified in the unit you provide. The size of a volumetric scene is immutable after creation.

This modifier affects only windows that have the volumetric style in visionOS.

## Sizing a window

- **Positioning and sizing windows**: Influence the initial geometry of windows that your app presents.
- **defaultSize(_:)**: Sets a default size for a window.
- **defaultSize(width:height:)**: Sets a default width and height for a window.
- **defaultSize(width:height:depth:)**: Sets a default size for a volumetric window.
- **defaultSize(width:height:depth:in:)**: Sets a default size for a volumetric window.
- **windowResizability(_:)**: Sets the kind of resizability to use for a window.
- **WindowResizability**: The resizability of a window.
- **windowIdealSize(_:)**: Specifies how windows derived form this scene should determine their size when zooming.
- **WindowIdealSize**: A type which defines the size a window should use when zooming.

