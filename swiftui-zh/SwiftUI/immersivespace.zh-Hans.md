---
来源： https://developer.apple.com/documentation/swiftui/immersivespace
抓取时间： 2025-12-03T05:33:32Z
---

# 沉浸式空间

**Structure**

在无边界空间中呈现内容的场景。

## 声明

```swift
struct ImmersiveSpace<Content, Data> where Content : ImmersiveSpaceContent, Data : Decodable, Data : Encodable, Data : Hashable
```

## 概览

将沉浸式空间用作应用程序显示的视图层次结构的容器。您声明为沉浸式空间内容的层次结构可作为其模板：

```swift
@main
struct SolarSystemApp: App {
    var body: some Scene {
        ImmersiveSpace {
            SolarSystem()
        }
    }
}
```

如果您想创建一个有边界的场景，请使用创建窗口或体积的类型，如 [WindowGroup](WindowGroup.zh-Hans.md) 或 [DocumentGroup](DocumentGroup.zh-Hans.md)。

###身临其境的空间风格

默认情况下，身临其境空间使用[mixed](ImmersionStyle/mixed.zh-Hans.md) 风格，将虚拟内容置于人的周围环境中。您可以在场景中添加[immersionStyle(selection:in:)](Scene/immersionStyle_selection_in.zh-Hans.md) 场景修改器，为身临其境空间选择不同的样式。例如，您可以使用[full](ImmersionStyle/full.zh-Hans.md)沉浸式风格完全控制视觉体验：

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

在呈现沉浸式空间后，您可以通过更改修改器的`selection` 输入来更改沉浸式风格，但只能使用修改器第二个参数中指定的其中一个值。对于任何沉浸样式，应用程序界面的其他部分（即窗口）都将保持可见。不过，沉浸风格会影响窗口与环境中虚拟对象的交互方式：

- 在 [mixed](ImmersionStyle/mixed.zh-Hans.md) 风格中，虚拟对象会遮住该对象后面的部分或全部窗口。同样，窗口也会遮盖窗口后面的虚拟对象。
- 对于其他样式，无论用户如何定位窗口或内容，窗口总是呈现在虚拟内容的前面。这可以帮助用户在部分或完全关闭穿透时，避免丢失虚拟内容后面的窗口。

#### 打开一个身临其境的空间

您可以通过给沉浸式空间一个标识符，以编程方式打开它。例如，你可以给前面例子中的太阳系视图贴上标签：

```swift
ImmersiveSpace(id: "solarSystem") {
    SolarSystem()
}
```

在代码的其他地方，你可以使用[openImmersiveSpace](EnvironmentValues/openImmersiveSpace.zh-Hans.md) 环境值来获取给定[OpenImmersiveSpaceAction](OpenImmersiveSpaceAction.zh-Hans.md) 结构的[Environment](Environment.zh-Hans.md) 实例。您可以使用标识符直接调用该实例，例如从按钮的闭合中调用，如下面的代码：

```swift
struct NewSolarSystemImmersiveSpace: View {
    var solarSystem: SolarSystem
    @Environment(\.openImmersiveSpace) private var openImmersiveSpace

    var body: some View {
        Button("Present Solar System") {
            Task {
                await openImmersiveSpace(id: "solarSystem")
            }
        }
    }
}
```

用`await`标记动作调用，因为它是异步执行的。当您的应用程序打开一个沉浸式空间时，系统会隐藏所有其他可见的应用程序。系统只允许同时打开一个沉浸式空间。在打开另一个沉浸式空间之前，请务必关闭已打开的沉浸式空间。

### 解散沉浸式空间

您可以通过调用环境中的[dismissImmersiveSpace](EnvironmentValues/dismissImmersiveSpace.zh-Hans.md)动作来取消沉浸式空间。例如，你可以定义一个按钮来解除沉浸式空间：

```swift
struct DismissImmersiveSpaceButton: View {
    @Environment(\.dismissImmersiveSpace)
    private var dismissImmersiveSpace

    var body: some View {
        Button("Close Solar System") {
            Task {
                await dismissImmersiveSpace()
            }
        }
    }
}
```

与打开动作一样，解散动作也是异步运行的。解散沉浸式空间时不需要指定标识符，因为同一时间只能有一个沉浸式空间打开。

### 启动时呈现一个沉浸式空间

当应用程序启动时，它会打开应用程序正文中列出的第一个场景的实例。不过，要在启动时打开一个沉浸式空间，您需要在应用程序的`Info.plist`文件中提供额外的配置信息。特别是，将场景清单中的[doc://com.apple.documentation/documentation/BundleResources/Information-Property-List/UIApplicationPreferredDefaultSceneSessionRole]键设置为[doc://com.apple.documentation/documentation/BundleResources/Information-Property-List/UIApplicationSceneManifest/UISceneConfigurations/UISceneSessionRoleImmersiveSpaceApplication]值。

要配置启动时打开的身临其境空间的样式，请向场景会话角色添加场景配置。使用[doc://com.apple.documentation/documentation/BundleResources/Information-Property-List/UIApplicationSceneManifest/UISceneConfigurations/UISceneSessionRoleImmersiveSpaceApplication/UISceneInitialImmersionStyle]键和一个表示混合、完整或渐进样式之一的值。有关更多信息，请参阅初始沉浸风格键。

## 创建沉浸式空间

- **init(content:)**：创建沉浸式空间。

## 识别身临其境的空间

- **init(id:content:)**：创建与指定标识符相关的沉浸式空间。

## 创建数据驱动的沉浸式空间

- **init(for:content:)**：为指定类型的展示数据创建沉浸式空间。
- **init(id:for:content:)**：为指定类型的呈现数据创建与标识符相关的沉浸式空间。

## 为沉浸式空间提供默认数据

- **init(for:content:defaultValue:)**：创建沉浸式空间。
- **init(id:for:content:defaultValue:)**：为指定类型的呈现数据创建与标识符相关联的沉浸式空间，如果未设置数据，则创建默认值。

## 支持类型

- **ImmersiveSpaceViewContent**：使用 SwiftUI 视图层次结构作为内容的沉浸式空间内容。
- **ImmersiveSpaceContent**：可用作沉浸式空间内容的类型。

## 初始化器

- **init(for:makeContent:)**
- **init(for:makeContent:defaultValue:)**
- **init(id:for:makeContent:)**
- **init(id:for:makeContent:defaultValue:)**
- **init(id:makeContent:)**：创建与指定标识符相关联的沉浸式空间。
- **init(makeContent:)**：创建与指定标识符相关联的沉浸式空间。

## 创建沉浸式空间

- **ImmersiveSpaceContentBuilder**：用于合成沉浸式空间元素集合的结果生成器。
- **immersionStyle(selection:in:)**：设置沉浸式空间的样式。
- **ImmersionStyle**：身临其境空间可具有的样式。
- **immersiveSpaceDisplacement**：将沉浸式空间从默认位置移开时，系统应用于该空间的位移，以米为单位。
- **ImmersiveEnvironmentBehavior**：当您的应用程序打开场景时，系统提供的沉浸式环境的行为。
- **ProgressiveImmersionAspectRatio**

## 符合

- 场景


---
source: https://developer.apple.com/documentation/swiftui/immersivespace
crawled: 2025-12-03T05:33:32Z
---

# ImmersiveSpace

**Structure**

A scene that presents its content in an unbounded space.

## Declaration

```swift
struct ImmersiveSpace<Content, Data> where Content : ImmersiveSpaceContent, Data : Decodable, Data : Encodable, Data : Hashable
```

## Overview

Use an immersive space as a container for a view hierarchy that your app presents. The hierarchy that you declare as the immersive space’s content serves as a template for it:

```swift
@main
struct SolarSystemApp: App {
    var body: some Scene {
        ImmersiveSpace {
            SolarSystem()
        }
    }
}
```

If you want to create a bounded scene instead, use one of the types that creates a window or a volume, like [WindowGroup](WindowGroup.zh-Hans.md) or [DocumentGroup](DocumentGroup.zh-Hans.md).

### Style the immersive space

By default, immersive spaces use the [mixed](ImmersionStyle/mixed.zh-Hans.md) style which places virtual content in a person’s surroundings. You can select a different style for the immersive space by adding the [immersionStyle(selection:in:)](Scene/immersionStyle_selection_in.zh-Hans.md) scene modifier to the scene. For example, you can completely control the visual experience using the [full](ImmersionStyle/full.zh-Hans.md) immersion style:

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

You can change the immersion style after presenting the immersive space by changing the modifier’s `selection` input, although you can only use one of the values that you specify in the modifier’s second parameter. For any style of immersion, the other parts of your app’s interface — namely its windows — remain visible. However, the immersion style affects how windows interact with virtual objects in the environment:

- For the [mixed](ImmersionStyle/mixed.zh-Hans.md) style, a virtual object obscures part or all of a window that’s behind the object. Similarly, a window obscures a virtual object that’s behind the window.
- For other styles, windows always render in front of virtual content, no matter how someone positions the window or the content. This helps people to avoid losing track of windows behind virtual content when passthrough is partially or completely off.

### Open an immersive space

You can programmatically open an immersive space by giving it an identifier. For example, you can label the solar system view from the previous example:

```swift
ImmersiveSpace(id: "solarSystem") {
    SolarSystem()
}
```

Elsewhere in your code, you use the [openImmersiveSpace](EnvironmentValues/openImmersiveSpace.zh-Hans.md) environment value to get the instance of the [OpenImmersiveSpaceAction](OpenImmersiveSpaceAction.zh-Hans.md) structure for a given [Environment](Environment.zh-Hans.md). You call the instance directly — for example, from a button’s closure, like in the following code — using the identifier:

```swift
struct NewSolarSystemImmersiveSpace: View {
    var solarSystem: SolarSystem
    @Environment(\.openImmersiveSpace) private var openImmersiveSpace

    var body: some View {
        Button("Present Solar System") {
            Task {
                await openImmersiveSpace(id: "solarSystem")
            }
        }
    }
}
```

Mark the call to the action with `await` because it executes asynchronously. When your app opens an immersive space, the system hides all other visible apps. The system allows only one immersive space to be open at a time. Be sure to close the open immersive space before opening another one.

### Dismiss an immersive space

You can dismiss an immersive space by calling the [dismissImmersiveSpace](EnvironmentValues/dismissImmersiveSpace.zh-Hans.md) action from the environment. For example, you can define a button that dismisses an immersive space:

```swift
struct DismissImmersiveSpaceButton: View {
    @Environment(\.dismissImmersiveSpace)
    private var dismissImmersiveSpace

    var body: some View {
        Button("Close Solar System") {
            Task {
                await dismissImmersiveSpace()
            }
        }
    }
}
```

The dismiss action runs asynchronously, like the open action. You don’t need to specify an identifier when dismissing an immersive space because there can only be one immersive space open at a time.

### Present an immersive space at launch

When an app launches, it opens an instance of the first scene that’s listed in the app’s body. However, to open an immersive space at launch, you need to provide additional configuration information in your app’s `Info.plist` file. In particular, set the [doc://com.apple.documentation/documentation/BundleResources/Information-Property-List/UIApplicationPreferredDefaultSceneSessionRole] key in the scene manifest to the value [doc://com.apple.documentation/documentation/BundleResources/Information-Property-List/UIApplicationSceneManifest/UISceneConfigurations/UISceneSessionRoleImmersiveSpaceApplication].

To configure the style of the immersive space that opens at launch, add a scene configuration to the scene session role. Use the [doc://com.apple.documentation/documentation/BundleResources/Information-Property-List/UIApplicationSceneManifest/UISceneConfigurations/UISceneSessionRoleImmersiveSpaceApplication/UISceneInitialImmersionStyle] key together with a value that indicates one of the mixed, full, or progressive styles. See the initial immersion style key for more information.

## Creating an immersive space

- **init(content:)**: Creates an immersive space.

## Identifying an immersive space

- **init(id:content:)**: Creates the immersive space associated with the specified identifier.

## Creating a data-driven immersive space

- **init(for:content:)**: Creates the immersive space for a specified type of presented data.
- **init(id:for:content:)**: Creates the immersive space associated with an identifier for a specified type of presented data.

## Providing default data to an immersive space

- **init(for:content:defaultValue:)**: Creates an immersive space.
- **init(id:for:content:defaultValue:)**: Creates the immersive space associated with an identifier for a specified type of presented data, and a default value, if the data is not set.

## Supporting types

- **ImmersiveSpaceViewContent**: Immersive space content that uses a SwiftUI view hierarchy as the content.
- **ImmersiveSpaceContent**: A type that you can use as the content of an immersive space.

## Initializers

- **init(for:makeContent:)**
- **init(for:makeContent:defaultValue:)**
- **init(id:for:makeContent:)**
- **init(id:for:makeContent:defaultValue:)**
- **init(id:makeContent:)**: Creates the immersive space associated with the specified identifier.
- **init(makeContent:)**

## Creating an immersive space

- **ImmersiveSpaceContentBuilder**: A result builder for composing a collection of immersive space elements.
- **immersionStyle(selection:in:)**: Sets the style for an immersive space.
- **ImmersionStyle**: The styles that an immersive space can have.
- **immersiveSpaceDisplacement**: The displacement that the system applies to the immersive space when moving the space away from its default position, in meters.
- **ImmersiveEnvironmentBehavior**: The behavior of the system-provided immersive environments when a scene is opened by your app.
- **ProgressiveImmersionAspectRatio**

## Conforms To

- Scene

