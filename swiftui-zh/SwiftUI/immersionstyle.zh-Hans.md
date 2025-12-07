---
来源： https://developer.apple.com/documentation/swiftui/immersionstyle
抓取时间： 2025-12-03T05:33:34Z
---

# 沉浸式风格

**Protocol**

沉浸式空间可以有的风格。

## 声明

```swift
protocol ImmersionStyle
```

## 概览

通过在空间中添加[immersionStyle(selection:in:)](Scene/immersionStyle_selection_in.zh-Hans.md) 场景修饰符，并指定符合本协议的样式（如[mixed](ImmersionStyle/mixed.zh-Hans.md) 或 [full](ImmersionStyle/full.zh-Hans.md)），来配置[ImmersiveSpace](ImmersiveSpace.zh-Hans.md) 的外观和行为。例如，下面的应用程序定义了一个使用完全沉浸式的太阳系场景：

```swift
@main
struct SolarSystemApp: App {
    @State private var style: ImmersionStyle = .full

    var body: some Scene {
        ImmersiveSpace {
            SolarSystem()
        }
        .immersionStyle(selection: $style, in: .full)
    }
}
```

## 获取内置样式

- **automatic**：默认沉浸样式。
- **full**：一种沉浸式样式，可显示完全取代直通视频的无限制内容。
- **mixed**：一种沉浸式样式，显示与其他应用程序内容混合的无限制内容，以及直通视频。
- **progressive**：沉浸式样式，显示部分取代直通视频的无限制内容。

## 支持类型

- **AutomaticImmersionStyle**：沉浸式空间的默认样式。
- **FullImmersionStyle**：一种沉浸式风格，可显示完全取代直通式视频的无限制内容。
- **MixedImmersionStyle**：一种沉浸式样式，显示与其他应用程序内容混合的无限制内容，以及直通视频。
- **ProgressiveImmersionStyle**：沉浸式样式，显示部分取代直通视频的无限制内容。

### 类型方法

- **progressive(_:initialAmount:)**：一种沉浸式样式，可显示部分取代直通视频的无限制内容。
- **progressive(_:initialAmount:aspectRatio:)**：一种沉浸式样式，可显示部分取代直通视频的无限制内容。
- **progressive(aspectRatio:)**：一种沉浸式样式，可显示部分取代直通视频的无限制内容。

## 创建沉浸式空间

- **ImmersiveSpace**：在无边界空间中呈现内容的场景。
- **ImmersiveSpaceContentBuilder**：用于合成沉浸式空间元素集合的结果生成器。
- **immersionStyle(selection:in:)**：设置沉浸式空间的样式。
- **immersiveSpaceDisplacement**：当沉浸式空间偏离默认位置时，系统应用于该空间的位移，单位为米。
- **ImmersiveEnvironmentBehavior**：当您的应用程序打开一个场景时，系统提供的沉浸式环境的行为。
- **ProgressiveImmersionAspectRatio**：当您的应用程序打开场景时，系统提供的沉浸式环境的行为。

## 符合类型

- 自动沉浸风格
- 全浸没样式
- 混合浸入式
- 渐进浸入式


---
source: https://developer.apple.com/documentation/swiftui/immersionstyle
crawled: 2025-12-03T05:33:34Z
---

# ImmersionStyle

**Protocol**

The styles that an immersive space can have.

## Declaration

```swift
protocol ImmersionStyle
```

## Overview

Configure the appearance and behavior of an [ImmersiveSpace](ImmersiveSpace.zh-Hans.md) by adding the [immersionStyle(selection:in:)](Scene/immersionStyle_selection_in.zh-Hans.md) scene modifier to the space and specifying a style that conforms to this protocol, like [mixed](ImmersionStyle/mixed.zh-Hans.md) or [full](ImmersionStyle/full.zh-Hans.md). For example, the following app defines a solar system scene that uses full immersion:

```swift
@main
struct SolarSystemApp: App {
    @State private var style: ImmersionStyle = .full

    var body: some Scene {
        ImmersiveSpace {
            SolarSystem()
        }
        .immersionStyle(selection: $style, in: .full)
    }
}
```

## Getting built-in styles

- **automatic**: The default immersion style.
- **full**: An immersion style that displays unbounded content that completely replaces passthrough video.
- **mixed**: An immersion style that displays unbounded content intermixed with other app content, along with passthrough video.
- **progressive**: An immersion style that displays unbounded content that partially replaces passthrough video.

## Supporting types

- **AutomaticImmersionStyle**: The default style of immersive spaces.
- **FullImmersionStyle**: An immersion style that displays unbounded content that completely replaces passthrough video.
- **MixedImmersionStyle**: An immersion style that displays unbounded content intermixed with other app content, along with passthrough video.
- **ProgressiveImmersionStyle**: An immersion style that displays unbounded content that partially replaces passthrough video.

## Type Methods

- **progressive(_:initialAmount:)**: An immersion style that displays unbounded content that partially replaces passthrough video.
- **progressive(_:initialAmount:aspectRatio:)**: An immersion style that displays unbounded content that partially replaces passthrough video.
- **progressive(aspectRatio:)**: An immersion style that displays unbounded content that partially replaces passthrough video.

## Creating an immersive space

- **ImmersiveSpace**: A scene that presents its content in an unbounded space.
- **ImmersiveSpaceContentBuilder**: A result builder for composing a collection of immersive space elements.
- **immersionStyle(selection:in:)**: Sets the style for an immersive space.
- **immersiveSpaceDisplacement**: The displacement that the system applies to the immersive space when moving the space away from its default position, in meters.
- **ImmersiveEnvironmentBehavior**: The behavior of the system-provided immersive environments when a scene is opened by your app.
- **ProgressiveImmersionAspectRatio**

## Conforming Types

- AutomaticImmersionStyle
- FullImmersionStyle
- MixedImmersionStyle
- ProgressiveImmersionStyle

