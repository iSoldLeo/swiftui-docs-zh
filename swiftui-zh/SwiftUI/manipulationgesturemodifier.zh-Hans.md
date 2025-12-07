---
来源： https://developer.apple.com/documentation/swiftui/manipulationgesturemodifier
抓取时间： 2025-12-02T17:47:44Z
---

# ManipulationGestureModifier | 苹果开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ ManipulationGestureModifier ](/documentation/swiftui/manipulationgesturemodifier)

- 操纵姿态修饰符

结构# ManipulationGestureModifier

visionOS 26.0+

```
nonisolated
struct ManipulationGestureModifier
```

## [关系](/documentation/swiftui/manipulationgesturemodifier#relationships)

### [Conforms To](/documentation/swiftui/manipulationgesturemodifier#conforms-to)

- [⟦ic_0013⟧](⟦lu_0029⟧)

## [See Also](/documentation/swiftui/manipulationgesturemodifier#see-also)

### [修改视图](/documentation/swiftui/manipulationgesturemodifier#Modifying-a-view)

[配置视图](/documentation/swiftui/configuring-views)通过应用视图修饰符调整视图的特性。 [减少视图修饰符维护](/documentation/swiftui/reducing-view-modifier-maintenance)将经常重复使用的视图修饰符捆绑到自定义视图修饰符中。[`func modifier<T>(T) -> ModifiedContent<Self, T>`](/documentation/swiftui/view/modifier(_:))将修改器应用到视图并返回一个新视图。 [`protocol ViewModifier`](/documentation/swiftui/viewmodifier))将修改器应用到视图或另一个视图修改器，生成原始值的不同版本。[`struct EmptyModifier`](/documentation/swiftui/emptymodifier)空修饰符或标识修饰符，在开发过程中用于在编译时切换修饰符。[`struct ModifiedContent`](/documentation/swiftui/modifiedcontent)应用了修饰符的值。[`protocol EnvironmentalModifier`](/documentation/swiftui/environmentalmodifier)使用前必须在环境中解析为具体修饰符的修饰符。[`struct ManipulableModifier`](/documentation/swiftui/manipulablemodifier)[`struct ManipulableResponderModifier`](/documentation/swiftui/manipulablerespondermodifier)[`struct ManipulableTransformBindingModifier`](/documentation/swiftui/manipulabletransformbindingmodifier)[`struct ManipulationGeometryModifier`](/documentation/swiftui/manipulationgeometrymodifier)[`struct ManipulationUsingGestureStateModifier`](/documentation/swiftui/manipulationusinggesturestatemodifier)[`enum Manipulable`](/documentation/swiftui/manipulable)A namespace for various manipulable related types.

---
source: https://developer.apple.com/documentation/swiftui/manipulationgesturemodifier
crawled: 2025-12-02T17:47:44Z
---

# ManipulationGestureModifier | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ ManipulationGestureModifier ](/documentation/swiftui/manipulationgesturemodifier)

-  ManipulationGestureModifier 

Structure# ManipulationGestureModifier

visionOS 26.0+

```
nonisolated
struct ManipulationGestureModifier
```

## [Relationships](/documentation/swiftui/manipulationgesturemodifier#relationships)

### [Conforms To](/documentation/swiftui/manipulationgesturemodifier#conforms-to)

- [`ViewModifier`](/documentation/swiftui/viewmodifier)

## [See Also](/documentation/swiftui/manipulationgesturemodifier#see-also)

### [Modifying a view](/documentation/swiftui/manipulationgesturemodifier#Modifying-a-view)

[Configuring views](/documentation/swiftui/configuring-views)Adjust the characteristics of a view by applying view modifiers.[Reducing view modifier maintenance](/documentation/swiftui/reducing-view-modifier-maintenance)Bundle view modifiers that you regularly reuse into a custom view modifier.[`func modifier<T>(T) -> ModifiedContent<Self, T>`](/documentation/swiftui/view/modifier(_:))Applies a modifier to a view and returns a new view.[`protocol ViewModifier`](/documentation/swiftui/viewmodifier)A modifier that you apply to a view or another view modifier, producing a different version of the original value.[`struct EmptyModifier`](/documentation/swiftui/emptymodifier)An empty, or identity, modifier, used during development to switch modifiers at compile time.[`struct ModifiedContent`](/documentation/swiftui/modifiedcontent)A value with a modifier applied to it.[`protocol EnvironmentalModifier`](/documentation/swiftui/environmentalmodifier)A modifier that must resolve to a concrete modifier in an environment before use.[`struct ManipulableModifier`](/documentation/swiftui/manipulablemodifier)[`struct ManipulableResponderModifier`](/documentation/swiftui/manipulablerespondermodifier)[`struct ManipulableTransformBindingModifier`](/documentation/swiftui/manipulabletransformbindingmodifier)[`struct ManipulationGeometryModifier`](/documentation/swiftui/manipulationgeometrymodifier)[`struct ManipulationUsingGestureStateModifier`](/documentation/swiftui/manipulationusinggesturestatemodifier)[`enum Manipulable`](/documentation/swiftui/manipulable)A namespace for various manipulable related types.