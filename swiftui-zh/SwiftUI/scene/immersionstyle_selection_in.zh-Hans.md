--- 来源：https://developer.apple.com/documentation/swiftui/scene/immersionstyle(selection:in:)

抓取时间：2025-12-01T10:22:37Z

---

# immersionStyle(selection:in:)

**实例方法**

设置沉浸式空间的样式。

## 声明

```swift
nonisolated func immersionStyle(selection: Binding<any ImmersionStyle>, in styles: any ImmersionStyle...) -> some Scene

```

## 参数

- **selection**：空间使用的样式。即使在呈现沉浸式空间之后，您也可以更改此值来更改场景的样式。即使您提供了绑定，该值也仅在您更改它时才会更改。

- **styles**：输入框可以具有的样式列表。请包含您计划在场景生命周期内使用的所有样式。

## 返回值

使用指定样式之一的场景。

## 说明

使用此修改器配置 [ImmersiveSpace](../ImmersiveSpace.zh-Hans.md) 的外观和行为。指定符合 [ImmersionStyle](../ImmersionStyle.zh-Hans.md) 协议的样式，例如 [mixed](../ImmersionStyle/mixed.zh-Hans.md) 或 [full](../ImmersionStyle/full.zh-Hans.md)。例如，以下应用程序定义了一个使用完全沉浸式效果的太阳系场景：

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

## 创建沉浸式空间

- **ImmersiveSpace**：在无界空间中呈现内容的场景。

- **ImmersiveSpaceContentBuilder**：用于组合沉浸式空间元素集合的结果构建器。

- **ImmersionStyle**：沉浸式空间可以拥有的样式。

- **immersiveSpaceDisplacement**：当沉浸式空间偏离其默认位置时，系统对其施加的位移量（以米为单位）。

- **ImmersiveEnvironmentBehavior**：当您的应用打开场景时，系统提供的沉浸式环境的行为。

- **ProgressiveImmersionAspectRatio**


---
source: https://developer.apple.com/documentation/swiftui/scene/immersionstyle(selection:in:)
crawled: 2025-12-01T10:22:37Z
---

# immersionStyle(selection:in:)

**Instance Method**

Sets the style for an immersive space.

## Declaration

```swift
nonisolated func immersionStyle(selection: Binding<any ImmersionStyle>, in styles: any ImmersionStyle...) -> some Scene

```

## Parameters

- **selection**: A [Binding](../Binding.zh-Hans.md) to the style that the space uses. You can change this value to change the scene’s style even after you present the immersive space. Even though you provide a binding, the value changes only if you change it.
- **styles**: The list of styles that the `selection` input can have. Include any styles that you plan to use during the lifetime of the scene.

## Return Value

A scene that uses one of the specified `styles`.

## Discussion

Use this modifier to configure the appearance and behavior of an [ImmersiveSpace](../ImmersiveSpace.zh-Hans.md). Specify a style that conforms to the [ImmersionStyle](../ImmersionStyle.zh-Hans.md) protocol, like [mixed](../ImmersionStyle/mixed.zh-Hans.md) or [full](../ImmersionStyle/full.zh-Hans.md). For example, the following app defines a solar system scene that uses full immersion:

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

## Creating an immersive space

- **ImmersiveSpace**: A scene that presents its content in an unbounded space.
- **ImmersiveSpaceContentBuilder**: A result builder for composing a collection of immersive space elements.
- **ImmersionStyle**: The styles that an immersive space can have.
- **immersiveSpaceDisplacement**: The displacement that the system applies to the immersive space when moving the space away from its default position, in meters.
- **ImmersiveEnvironmentBehavior**: The behavior of the system-provided immersive environments when a scene is opened by your app.
- **ProgressiveImmersionAspectRatio**

