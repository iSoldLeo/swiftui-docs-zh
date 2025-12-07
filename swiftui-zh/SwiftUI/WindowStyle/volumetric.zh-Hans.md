---
来源： https://developer.apple.com/documentation/SwiftUI/WindowStyle/volumetric
抓取时间： 2025-12-02T16:21:20Z
---

# 体积

**类型属性**

创建三维体积窗口的窗口样式。

## 声明

```swift
static var volumetric: VolumetricWindowStyle { get }
```

## 讨论

使用体积窗口（或*体积*）来显示限定区域内的三维内容。例如，[doc://com.apple.documentation/documentation/visionOS/World] 使用一个体积来显示`Globe` 模型，人们可以拿起模型并使用窗口栏在共享空间中移动：

```swift
WindowGroup(id: Module.globe.name) {
    Globe()
        .environment(model)
}
.windowStyle(.volumetric)
.defaultSize(width: 0.6, height: 0.6, depth: 0.6, in: .meters)
```

与其他窗口不同的是，当人们在窗口周围移动时，音量会逐渐减弱。此外，与其他窗口不同的是，volume 使用固定比例，这意味着当 volume 离得较远时，volume 中的物体会显得较小，就像真实物体一样。有关固定比例和动态比例的比较，请参阅《人机界面指南》中的[doc://com.apple.documentation/design/Human-Interface-Guidelines/spatial-layout#Scale]。

您可以使用其中一个默认尺寸场景修改器（如 [defaultSize(width:height:depth:in:)](../scene/defaultSize_width_height_depth_in.zh-Hans.md)）为体指定一个尺寸。由于体积使用的是固定比例，以物理单位（如米）指定尺寸通常比较方便，如上面的代码所示。卷出现后，人们无法更改它的大小。



有关设计指导，请参阅《人机界面指南》中的[doc://com.apple.documentation/design/Human-Interface-Guidelines/windows#Volumes]。如果要在整个共享空间或完整空间中任意放置 3D 物体，请使用 [ImmersiveSpace](../ImmersiveSpace.zh-Hans.md) 代替。

## 获取内置窗口样式

- **automatic**：默认窗口样式。
- **hiddenTitleBar**：一种隐藏窗口标题和标题栏后部区域的窗口样式，允许显示更多的窗口内容。
- **plain**：普通窗口样式。
- **titleBar**：显示窗口标题栏部分的窗口样式。


---
source: https://developer.apple.com/documentation/SwiftUI/WindowStyle/volumetric
crawled: 2025-12-02T16:21:20Z
---

# volumetric

**Type Property**

A window style that creates a 3D volumetric window.

## Declaration

```swift
static var volumetric: VolumetricWindowStyle { get }
```

## Discussion

Use a volumetric window — or a *volume* — to display 3D content within a bounded region. For example, [doc://com.apple.documentation/documentation/visionOS/World] uses a volume to present a `Globe` model that people can pick up and move around the Shared Space using the window bar:

```swift
WindowGroup(id: Module.globe.name) {
    Globe()
        .environment(model)
}
.windowStyle(.volumetric)
.defaultSize(width: 0.6, height: 0.6, depth: 0.6, in: .meters)
```

A volume enables someone to view content from all angles, unlike other windows which fade out as people move around the window. Also unlike other windows, a volume uses fixed scale, which means that objects in the volume appear smaller when the volume is farther away, like real objects would. For a comparison of fixed and dynamic scale, see [doc://com.apple.documentation/design/Human-Interface-Guidelines/spatial-layout#Scale] in the Human Interface Guidelines.

You can specify a size for the volume using one of the default size scene modifiers, like [defaultSize(width:height:depth:in:)](../scene/defaultSize_width_height_depth_in.zh-Hans.md). Because volumes use fixed scale, it’s typically convenient to specify a size in physical units — like meters, as the above code demonstrates. People can’t change the size of the volume after it appears.



For design guidance, see [doc://com.apple.documentation/design/Human-Interface-Guidelines/windows#Volumes] in the Human Interface Guidelines. If you want to place 3D objects arbitrarily throughout the Shared Space or in a Full Space, use an [ImmersiveSpace](../ImmersiveSpace.zh-Hans.md) instead.

## Getting built-in window styles

- **automatic**: The default window style.
- **hiddenTitleBar**: A window style which hides both the window’s title and the backing of the titlebar area, allowing more of the window’s content to show.
- **plain**: The plain window style.
- **titleBar**: A window style which displays the title bar section of the window.

