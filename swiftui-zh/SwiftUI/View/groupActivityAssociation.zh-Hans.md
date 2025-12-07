--- 来源：https://developer.apple.com/documentation/SwiftUI/View/groupActivityAssociation(_:)

抓取时间：2025-12-02T17:23:54Z

---

# groupActivityAssociation(_:)

**实例方法**

指定视图应如何与当前 SharePlay 群组活动关联。

## 声明

```swift
nonisolated func groupActivityAssociation(_ kind: GroupActivityAssociationKind?) -> some View

```

## 参数

- **kind**：如果指定，则指定群组活动关联的类型。

```swift
  You can dynamically remove the group activity's association with a view by
  setting the given `kind` to `nil` instead of `.primary(_:)`.
```

## 说明

当一群人使用他们的空间角色加入 SharePlay 活动时，系统会选择一个公共的主场景来围绕该场景安排他们的空间角色。群组活动与应用中的主场景之间的这种关联会创建一个共享空间，供空间角色进行交互；允许参与者通过手势指向关联场景并相互理解。有关 visionOS 上的空间 Personas 和 SharePlay 的更多信息，请参阅文档：为 activity 添加空间 Persona 支持。

默认情况下，系统会结合场景的激活条件和 activity 的 `SceneAssociationBehavior` 来选择要与 activity 关联的场景。您可以使用此修饰符将视图的组活动关联设置为 `GroupActivityAssociationKind/primary`，从而指定不同的场景或动态更改关联的场景。

```swift
struct MyApp: App {
    var body: some Scene {
        ...
        Window("Game Window") {
            GameView()
                .groupActivityAssociation(.primary("game-window"))
        }
    }
}
```

如果同时配置了多个具有主组活动关联的场景，则会使用最近关联的场景。例如，如果您的应用定义了两个窗口，并且这两个窗口都包含具有主关联类型的视图，则最近打开的窗口将用作主场景。如果第二个窗口随后关闭，则会再次使用原始窗口。

您可以通过将给定类型设置为 `nil` 而不是 `.primary`，动态移除群组活动与视图的关联。

```swift
@State var activityState: ActivityState

var body: some Scene {
    WindowGroup {
        TeamSelectionView()
            .groupActivityAssociation(activityState == .teamSelection ? .primary("team-selection") : nil)
    }

    WindowGroup {
        CardGameVolume()
            .groupActivityAssociation(activityState == .inGame ? .primary("in-game") : nil)
    }
    .windowStyle(.volumetric)
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/View/groupActivityAssociation(_:)
crawled: 2025-12-02T17:23:54Z
---

# groupActivityAssociation(_:)

**Instance Method**

Specifies how a view should be associated with the current SharePlay group activity.

## Declaration

```swift
nonisolated func groupActivityAssociation(_ kind: GroupActivityAssociationKind?) -> some View

```

## Parameters

- **kind**: If given, the kind of group activity association.

```swift
  You can dynamically remove the group activity's association with a view by
  setting the given `kind` to `nil` instead of `.primary(_:)`.
```

## Discussion

When a group of people join a SharePlay activity with their spatial Personas, the system selects a common, primary scene to arrange their spatial Personas around. This association between the group activity and a primary scene in your app creates a shared space for the spatial Personas to interact in; enabling participants to gesture at the associated scene and understand each other. For more information about spatial Personas and  SharePlay on visionOS, see doc:adding-spatial-persona-support-to-an-activity.

By default, the system uses your scene’s activation conditions in concert with your activity’s `SceneAssociationBehavior` to select a scene to associate with the activity. You can specify a different scene or dynamically change the associated scene by using this modifier to set a view’s group activity association to `GroupActivityAssociationKind/primary`.



```swift
struct MyApp: App {
    var body: some Scene {
        ...
        Window("Game Window") {
            GameView()
                .groupActivityAssociation(.primary("game-window"))
        }
    }
}
```

If there are multiple scenes that are simultaneously configured with the primary group activity association, the most recently associated scene will be used. For example, if your app defines two windows and both contain views with the primary association kind, the most recently opened one will be used as the primary scene. If that second window is subsequently closed, the original window will be used again.

You can dynamically remove the group activity’s association with a view by setting the given kind to `nil` instead of `.primary`.

```swift
@State var activityState: ActivityState

var body: some Scene {
    WindowGroup {
        TeamSelectionView()
            .groupActivityAssociation(activityState == .teamSelection ? .primary("team-selection") : nil)
    }

    WindowGroup {
        CardGameVolume()
            .groupActivityAssociation(activityState == .inGame ? .primary("in-game") : nil)
    }
    .windowStyle(.volumetric)
}
```

