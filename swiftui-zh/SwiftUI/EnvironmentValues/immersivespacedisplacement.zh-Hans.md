---
来源： https://developer.apple.com/documentation/swiftui/environmentvalues/immersivespacedisplacement
抓取时间： 2025-12-03T05:33:35Z
---

# 沉浸式空间位移

**实例属性**

将沉浸式空间从默认位置移开时，系统应用于沉浸式空间的位移，以米为单位。

## 声明

```swift
var immersiveSpaceDisplacement: Pose3D { get }
```

## 讨论

默认情况下，系统会将身临其境空间的原点放在地面上，即人的脚下。加入共享活动时，系统会将沉浸式空间移动到适合所有参与者的位置。当参与者加入和离开活动时，参与者和沉浸式空间的位置都会更新。读取此属性可获得沉浸式空间相对于其默认位置的当前偏移量。

如果在开放的沉浸式空间外访问此属性，它将包含 [doc://com.apple.documentation/documentation/Spatial/Pose3D/identity]。

如果您在共享活动中显示特定于参与者的视图或实体，请使用此位移值的倒数来定位这些视图和实体在沉浸式空间中的位置。应用逆值将它们定位为单个参与者沉浸式空间中的视图和实体。

在下面的示例中，应用此值是为了将游戏 HUD 实体定位在人的位置，而不是共享活动的位置：

```swift
@main
struct GameApp: App {
    var body: some Scene {
        ImmersiveSpace {
            ImmersiveGameView()
        }
    }
}

struct ImmersiveGameView: View {
    @Environment(\.immersiveSpaceDisplacement) private var immersiveSpaceDisplacement

    let gameHUDEntity = makeGameHUDEntity()

    var body: some View {
        RealityView { content in
            // ...
        } update: { content in
            let inverseDisplacement = float4x4(immersiveSpaceDisplacement.inverse)
            gameHUDEntity.setTransformMatrix(inverseDisplacement, relativeTo: nil)
        }
    }
}
```

## 创建一个身临其境的空间

- **ImmersiveSpace**：在无边界空间中呈现内容的场景。
- **ImmersiveSpaceContentBuilder**：用于合成沉浸式空间元素集合的结果生成器。
- **immersionStyle(selection:in:)**：设置沉浸式空间的样式。
- **ImmersionStyle**：身临其境空间可具有的样式。
- **ImmersiveEnvironmentBehavior**：当您的应用程序打开一个场景时，系统提供的沉浸式环境的行为。
- **ProgressiveImmersionAspectRatio**：当您的应用程序打开场景时，系统提供的沉浸式环境的行为。


---
source: https://developer.apple.com/documentation/swiftui/environmentvalues/immersivespacedisplacement
crawled: 2025-12-03T05:33:35Z
---

# immersiveSpaceDisplacement

**Instance Property**

The displacement that the system applies to the immersive space when moving the space away from its default position, in meters.

## Declaration

```swift
var immersiveSpaceDisplacement: Pose3D { get }
```

## Discussion

By default, the system places the origin of the immersive space at floor level, at the person’s feet. When joining a shared activity, the system moves the immersive space to an appropriate location for all participants. As participants join and leave the activity, the location of participants and the immersive space can update. Read this property to get the current offset of the immersive space relative to its default position.

If you access this property outside of an open immersive space, it contains the value [doc://com.apple.documentation/documentation/Spatial/Pose3D/identity].

If you display participant-specific views or entities in your shared activity, use the inverse of this displacement value to position those views and entities in the immersive space. Applying the inverse value positions them as if they were in a single-participant immersive space.

In the following example, this value is applied to position a game HUD entity at the person’s location, rather than the shared activity’s location:

```swift
@main
struct GameApp: App {
    var body: some Scene {
        ImmersiveSpace {
            ImmersiveGameView()
        }
    }
}

struct ImmersiveGameView: View {
    @Environment(\.immersiveSpaceDisplacement) private var immersiveSpaceDisplacement

    let gameHUDEntity = makeGameHUDEntity()

    var body: some View {
        RealityView { content in
            // ...
        } update: { content in
            let inverseDisplacement = float4x4(immersiveSpaceDisplacement.inverse)
            gameHUDEntity.setTransformMatrix(inverseDisplacement, relativeTo: nil)
        }
    }
}
```

## Creating an immersive space

- **ImmersiveSpace**: A scene that presents its content in an unbounded space.
- **ImmersiveSpaceContentBuilder**: A result builder for composing a collection of immersive space elements.
- **immersionStyle(selection:in:)**: Sets the style for an immersive space.
- **ImmersionStyle**: The styles that an immersive space can have.
- **ImmersiveEnvironmentBehavior**: The behavior of the system-provided immersive environments when a scene is opened by your app.
- **ProgressiveImmersionAspectRatio**

