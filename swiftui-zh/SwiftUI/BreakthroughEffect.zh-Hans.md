---
来源：https://developer.apple.com/documentation/SwiftUI/BreakthroughEffect
抓取时间： 2025-12-02T17:32:53Z
---

# BreakthroughEffect | 苹果开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ 突破效果 ](/documentation/SwiftUI/BreakthroughEffect)

- 突破效应

结构# 突破效应

visionOS 26.0+

```
struct BreakthroughEffect
```

## [主题](/documentation/SwiftUI/BreakthroughEffect#topics)

### [类型属性](/documentation/SwiftUI/BreakthroughEffect#Type-Properties)

[系统将根据元素类型及其在场景中的位置选择最佳效果。这可能导致没有突破性效果。[`static let none: BreakthroughEffect`](/documentation/swiftui/breakthrougheffect/none)元素被遮挡内容剪切。当用于自定义片材突破效果时，不支持此功能。[`static let prominent: BreakthroughEffect`](/documentation/swiftui/breakthrougheffect/prominent)元素通过遮挡内容突出显示。[`static let subtle: BreakthroughEffect`](/documentation/swiftui/breakthrougheffect/subtle)元素被巧妙地混合在遮挡内容中。## [关系](/documentation/SwiftUI/BreakthroughEffect#relationships)

### [Conforms To](/documentation/SwiftUI/BreakthroughEffect#conforms-to)

- [⟦ic_0006⟧](⟦lu_0017⟧)

- [⟦ic_0005⟧](⟦lu_0016⟧)

- [⟦ic_0004⟧](⟦lu_0015⟧)

## [See Also](/documentation/SwiftUI/BreakthroughEffect#see-also)

### [配置直通](/documentation/SwiftUI/BreakthroughEffect#Configuring-passthrough)

[`func preferredSurroundingsEffect(SurroundingsEffect?) -> some View`](/documentation/swiftui/view/preferredsurroundingseffect(_:))为直通视频应用效果。

---
source: https://developer.apple.com/documentation/SwiftUI/BreakthroughEffect
crawled: 2025-12-02T17:32:53Z
---

# BreakthroughEffect | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ BreakthroughEffect ](/documentation/SwiftUI/BreakthroughEffect)

-  BreakthroughEffect 

Structure# BreakthroughEffect

visionOS 26.0+

```
struct BreakthroughEffect
```

## [Topics](/documentation/SwiftUI/BreakthroughEffect#topics)

### [Type Properties](/documentation/SwiftUI/BreakthroughEffect#Type-Properties)

[`static let automatic: BreakthroughEffect`](/documentation/swiftui/breakthrougheffect/automatic)The system will choose the best effect for the type of element and its position within the scene. This might result in no breakthrough effect.[`static let none: BreakthroughEffect`](/documentation/swiftui/breakthrougheffect/none)The element is clipped by occluding content. This is not supported when used to customize a sheet breakthrough effect.[`static let prominent: BreakthroughEffect`](/documentation/swiftui/breakthrougheffect/prominent)The element is prominently revealed through occluding content.[`static let subtle: BreakthroughEffect`](/documentation/swiftui/breakthrougheffect/subtle)The element is subtly blended over occluding content.## [Relationships](/documentation/SwiftUI/BreakthroughEffect#relationships)

### [Conforms To](/documentation/SwiftUI/BreakthroughEffect#conforms-to)

- [`Equatable`](/documentation/Swift/Equatable)

- [`Sendable`](/documentation/Swift/Sendable)

- [`SendableMetatype`](/documentation/Swift/SendableMetatype)

## [See Also](/documentation/SwiftUI/BreakthroughEffect#see-also)

### [Configuring passthrough](/documentation/SwiftUI/BreakthroughEffect#Configuring-passthrough)

[`func preferredSurroundingsEffect(SurroundingsEffect?) -> some View`](/documentation/swiftui/view/preferredsurroundingseffect(_:))Applies an effect to passthrough video.[`struct SurroundingsEffect`](/documentation/swiftui/surroundingseffect)Effects that the system can apply to passthrough video.