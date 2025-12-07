--- 来源：https://developer.apple.com/documentation/SwiftUI/ProgressiveImmersionAspectRatio

抓取时间：2025-12-02T17:21:55Z

---

# ProgressiveImmersionAspectRatio | Apple 开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ ProgressiveImmersionAspectRatio ](/documentation/SwiftUI/ProgressiveImmersionAspectRatio)

- ProgressiveImmersionAspectRatio 

Structure# ProgressiveImmersionAspectRatio

macOS 26.0+ 和 macOS 26.0+

```
struct ProgressiveImmersionAspectRatio
```

## [主题](/documentation/SwiftUI/ProgressiveImmersionAspectRatio#topics)

### [类型属性](/documentation/SwiftUI/ProgressiveImmersionAspectRatio#Type-Properties)

[`static var automatic: ProgressiveImmersionAspectRatio`](/documentation/swiftui/progressiveimmersionaspectratio/automatic)系统将选择默认的门户宽高比。[`static var landscape: ProgressiveImmersionAspectRatio`](/documentation/swiftui/progressiveimmersionaspectratio/landscape)门户将宽阔。[`static var portrait: ProgressiveImmersionAspectRatio`](/documentation/swiftui/progressiveimmersionaspectratio/portrait)传送门将很高。## [关联关系](/documentation/SwiftUI/ProgressiveImmersionAspectRatio#relationships)

### [符合](/documentation/SwiftUI/ProgressiveImmersionAspectRatio#conforms-to)

- [`Equatable`](/documentation/Swift/Equatable)

- [`Sendable`](/documentation/Swift/Sendable)

- [`SendableMetatype`](/documentation/Swift/SendableMetatype)

## [另请参阅](/documentation/SwiftUI/ProgressiveImmersionAspectRatio#see-also)

### [创建沉浸式体验] [/documentation/SwiftUI/ProgressiveImmersionAspectRatio#Creating-an-immersive-space]

[`struct ImmersiveSpace`](/documentation/swiftui/immersivespace)在无界空间中呈现内容的场景。[`struct ImmersiveSpaceContentBuilder`](/documentation/swiftui/immersivespacecontentbuilder)用于构建沉浸式空间元素集合的结果构建器。[`func immersionStyle(selection: Binding<any ImmersionStyle>, in: any ImmersionStyle...) -> some Scene`](/documentation/swiftui/scene/immersionstyle(selection:in:)设置沉浸式空间的样式。[`protocol ImmersionStyle`](/documentation/swiftui/immersionstyle)沉浸式空间可以拥有的样式。[`var immersiveSpaceDisplacement: Pose3D`](/documentation/swiftui/environmentvalues/immersivespacedisplacement)当沉浸式空间偏离其默认位置时，系统对其施加的位移。米。[`struct ImmersiveEnvironmentBehavior`](/documentation/swiftui/immersiveenvironmentbehavior)当您的应用打开场景时，系统提供的沉浸式环境的行为。

---
source: https://developer.apple.com/documentation/SwiftUI/ProgressiveImmersionAspectRatio
crawled: 2025-12-02T17:21:55Z
---

# ProgressiveImmersionAspectRatio | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ ProgressiveImmersionAspectRatio ](/documentation/SwiftUI/ProgressiveImmersionAspectRatio)

-  ProgressiveImmersionAspectRatio 

Structure# ProgressiveImmersionAspectRatio

macOS 26.0+visionOS 26.0+

```
struct ProgressiveImmersionAspectRatio
```

## [Topics](/documentation/SwiftUI/ProgressiveImmersionAspectRatio#topics)

### [Type Properties](/documentation/SwiftUI/ProgressiveImmersionAspectRatio#Type-Properties)

[`static var automatic: ProgressiveImmersionAspectRatio`](/documentation/swiftui/progressiveimmersionaspectratio/automatic)The system will choose a default portal aspect ratio.[`static var landscape: ProgressiveImmersionAspectRatio`](/documentation/swiftui/progressiveimmersionaspectratio/landscape)The portal will be wide.[`static var portrait: ProgressiveImmersionAspectRatio`](/documentation/swiftui/progressiveimmersionaspectratio/portrait)The portal will be tall.## [Relationships](/documentation/SwiftUI/ProgressiveImmersionAspectRatio#relationships)

### [Conforms To](/documentation/SwiftUI/ProgressiveImmersionAspectRatio#conforms-to)

- [`Equatable`](/documentation/Swift/Equatable)

- [`Sendable`](/documentation/Swift/Sendable)

- [`SendableMetatype`](/documentation/Swift/SendableMetatype)

## [See Also](/documentation/SwiftUI/ProgressiveImmersionAspectRatio#see-also)

### [Creating an immersive space](/documentation/SwiftUI/ProgressiveImmersionAspectRatio#Creating-an-immersive-space)

[`struct ImmersiveSpace`](/documentation/swiftui/immersivespace)A scene that presents its content in an unbounded space.[`struct ImmersiveSpaceContentBuilder`](/documentation/swiftui/immersivespacecontentbuilder)A result builder for composing a collection of immersive space elements.[`func immersionStyle(selection: Binding<any ImmersionStyle>, in: any ImmersionStyle...) -> some Scene`](/documentation/swiftui/scene/immersionstyle(selection:in:))Sets the style for an immersive space.[`protocol ImmersionStyle`](/documentation/swiftui/immersionstyle)The styles that an immersive space can have.[`var immersiveSpaceDisplacement: Pose3D`](/documentation/swiftui/environmentvalues/immersivespacedisplacement)The displacement that the system applies to the immersive space when moving the space away from its default position, in meters.[`struct ImmersiveEnvironmentBehavior`](/documentation/swiftui/immersiveenvironmentbehavior)The behavior of the system-provided immersive environments when a scene is opened by your app.